// retrieve a collection
db.collection('documents')
  .get()
  .then(querySnapshot => {
    const documents = querySnapshot.docs.map(doc => doc.data())
    // do something with documents
  })

// retrieve a document
db.collection('documents')
  .doc(documentId)
  .get()
  .then(snapshot => {
    const document = snapshot.data()
    // do something with document
  })