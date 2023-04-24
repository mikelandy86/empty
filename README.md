db.adminCommand({ listDatabases: 1 }).databases.forEach(function(databaseInfo) {
    var dbName = databaseInfo.name;
    var dbInstance = db.getSiblingDB(dbName);
    
    dbInstance.getCollectionNames().forEach(function(collection) {
        var indexes = dbInstance[collection].getIndexes();
        print("Indexes for collection '" + collection + "' in database '" + dbName + "':");
        printjson(indexes);
    });
});
