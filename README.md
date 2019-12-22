# AngularRouter

npm install --save @ng-bootstrap/ng-bootstrap

import ng bootstrap module
import { NgbModule } from '@ng-bootstrap/ng-bootstrap'

Also, add it to @NgModule imports array.

imports: [
  BrowserModule,
  AppRoutingModule,
  NgbModule
],


Add this stylesheet reference to the Bootstrap stylesheet in the index.html before the closing of head tag.

<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" />


