
Clarify scope. Ask questions, determine what scale and customer base you're building for. 
For example, for the Google Drive app, are you building for people who have spotty Internet connections? 
Will you have to support all file types or only images? Will files have to deal with sharing/edit permissions? 
Will you have to support anonymous viewers? Etc etc

Once you get a good idea of what you're building for, write the data models. 
For Drive example, perhaps a File model and User model that contains uuid, permissions, group memberships.
Everything after the models is kind of pick and choose, depending on what you're most interested in:

