let found = false;

db.adminCommand("listDatabases").databases.forEach(function(d){
   let mdb = db.getSiblingDB(d.name);
   mdb.getCollectionInfos( ).forEach(function(c){
      namespace = d.name + "." + c.name;
      namespacelenBytes = encodeURIComponent(namespace).length;
      if (namespacelenBytes > 120) {
         found = true;
         print(c.type.toUpperCase() + " namespace exceeds 120 bytes:: " + namespace);
      }
   });
});

if (!found) {
   print("No namespaces exceeding 120 bytes were found.");
}
