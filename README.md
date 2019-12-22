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


Next, we have to modify the `src/app/app.component.html` file to replace all HTML tags except <router-outlet></router-outlet> tag.

<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" routerLink="">Angular Routing</a>
  <button class="navbar-toggler" type="button" (click)="toggleNavbar()" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" [ngClass]="{ 'show': navbarOpen }">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" routerLink="" routerLinkActive="active">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" routerLink="about" routerLinkActive="active">About Us</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" routerLink="privacy" routerLinkActive="active">Privacy Policy</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" routerLink="terms" routerLinkActive="active">Terms and Conditions</a>
      </li>
    </ul>
  </div>
</nav>

<div class="container">
  <router-outlet></router-outlet>
</div>