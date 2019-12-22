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


# Adding routes

create components

ng g component Home
ng g component About
ng g component Gallery
ng g component PageNotFound

we have to add routing for those components by open and edit `src/app/app-routing.module.ts` then add those components imports.

import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';
import { GalleryComponent } from './gallery/gallery.component';
import { PageNotFoundComponent } from './page-not-found/page-not-found.component';

Next, add or modify the constant variable of routes by this array of component routes.

const routes: Routes = [
  { path: 'home', component: HomeComponent },
  { path: 'about', component: AboutComponent },
  { path: 'gallery', component: GalleryComponent },
  { path: '', redirectTo: '/home', pathMatch: 'full' },
  { path: '**', component: PageNotFoundComponent }
];



