use admin
db.system.users.find({}, {user: 1, credentials: 1, _id: 0})
