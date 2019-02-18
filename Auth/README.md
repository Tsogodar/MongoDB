# How to enable MongoDB auth

## Step 1

    use admin
    db.createUser(
    {
        user: "admin",
        pwd: "admin",
        roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]
     }
    )

## Step 2

In `mongod.cfg` replace `#security` with `security: authorization: enabled`

## Step 3

Restart mongodb service

## Step 4

To auth use:

    use admin
    db.auth("admin","admin")
