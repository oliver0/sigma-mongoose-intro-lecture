Naughty or Nice Tracker with Mongo/Mongoose and Angular
Mongo can be really flexible and Mongoose gives us some handy features. You're going to be using these to finish building our Naught-Nice Tracker, just in time for the Holidays!

Niceness Level Tracking
Add a birthDate field.
Add a field of nicenessLevel. This will store a number from 1 to 5.
Add a drop-down in the entry form for saving this nicenessLevel
Mongoose Schema Data Types

Make sure these fields are carried through to the Mongoose Schema/Model. Show these new fields on the DOM.

Hard Mode
When you display each person on the page, if their nicenessLevel is less than 4, display that they are Naughty. Otherwise, they are Nice. Style their card differently based on this result.
Allow each person's nicenessLevel to be edited. You'll need to change our rather lame PUT/Update code to allow for this as well as allow for an interface on the DOM.
Pro Mode
Add an array to the Person Schema to store their Christmas wishlist items. This new array will have its own Schema and is called a Subdocument in Mongoose lingo.

var personSchema = new Schema({
    name: {type: String, required: true},
    location: String,
    // other fields from above modes //
    wishlist: [XMasItem]
});
In a new model .js file, define the new Schema. Something like:

var mongoose = require('mongoose');
var Schema = mongoose.Schema;

// subdocument
var christmasItem = new Schema({
  thing: { type: String, required: true }
});

var XMasItem = mongoose.model('XMasItem', christmasItem);

module.exports = XMasItem;
Change the person display cards to include a way to add wishlist items to a person and then display them. On the server, you'll have to findById to get the person and then find a way to push an item onto the array. Recall you can push onto arrays!
