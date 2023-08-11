# Learning Ionic

## What is Ionic

Ionic is a framework for building cross-platform mobile apps with HTML, CSS, and JavaScript. It's built on top of AngularJS and Apache Cordova. It provides tools and services for building Mobile UI with native look and feel.

### What is Apache Cordova

Apache Cordova is a platform for building native mobile applications using HTML, CSS and JavaScript.

### What is AngularJS

AngularJS is a JavaScript framework for building web applications and apps in JavaScript, html, and TypeScript, which is a superset of JavaScript.

## How to add a component in Ionic

Let the component name be header.
To add a component in Ionic, use the following command:

```bash
ionic g component <component-name>
```

Now you have got a template(header folder) for the component in app folder.
The header folder will contain the following files:

1. header.component.html
2. header.component.scss
3. header.component.spec.ts
4. header.component.ts

### How to use a component in Ionic

1. Go to the folder of the page on which you want to add the component. Add the following code in the (tab2.module.ts file):
  
    ```typescript
    // add the component in imports
    import { HeaderComponent } from '../header/header.component';

    @NgModule({
      imports: [
        IonicModule,
        CommonModule,
        FormsModule,
        ExploreContainerComponentModule,
        Tab2PageRoutingModule
      ],
      // add the component in declarations
      declarations: [Tab2Page, HeaderComponent]
    })
    export class Tab2PageModule {}
    ```

2. Go to the page (tab2.page.html) where you want to use the component and add the following code:

  ```html
  <app-header></app-header>
  ```

## How to add a page in Ionic

Let the page name be contact-us.
To add a page in Ionic, use the following command to generate the page:

```bash
ionic g page <page-name>
```

Now you have got a template(contact-us folder) for the page in app folder.
The page will be added to the app-routing.module.ts file.
Tt will contain the following files:

1. contact-us-routing.module.ts
2. contact-us.module.ts
3. contact-us.page.html
4. contact-us.page.scss
5. contact-us.page.spec.ts
6. contact-us.page.ts

### How to link a page in Ionic

1. For routing, go to (app-routing.module.ts) and add the following code (automatically added):

    ```typescript
    {
        path: 'contact-us',
        loadChildren: () => import('./contact-us/contact-us.module').then( m => m.ContactUsPageModule)
    }
    ```

2. Go to the page(tab2.page.html) where you want to add the link and add the following code:

    ```html
    <ion-button [routerLink]="['/contact-us']">Go to contact-us page</ion-button>
    ```

3. Add this to page (tab2-routing.module.ts) on which you want to add the link:

    ```typescript
    const routes: Routes = [
    {
      path: '',
      component: Tab2Page,
    },
    // add this code
    {
      path: 'contact-us',
      loadChildren: () => import('../contact-us/contact-us.module').then( m => m.ContactUsPageModule)
    },

    ];
    ```
