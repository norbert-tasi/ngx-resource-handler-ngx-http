# @ngx-resource/handler-ngx-http

It's implementation of `ResourceHandler` which uses Angular `HttpClient`

## How to install and setup it
```bash
& npm i --save @ngx-resource/core @ngx-resource/handler-ngx-http
```

In you app module
```typescript

// AoT requires an exported function for factories
export function myHandlerFactory(http: HttpClient) {
    return new MyResourceHandler(http);
}

@NgModule({
  imports: [
    BrowserModule,
    BrowserAnimationsModule,
    HttpClientModule,

    // Default ResourceHandler uses class `ResourceHandlerHttpClient`
    ResourceModule.forRoot()
    
    // Or set you own handler
    //ResourceModule.forRoot({
    //  handler: { provide: ResourceHandler, useFactory: (myHandlerFactory), deps: [HttpClient] }
    //})
  ],
  declarations: [...],
  bootstrap: [...],
  entryComponents: [...],
  providers: [...]
})
export class AppModule {
}
```

## [Docs about rest-core](https://github.com/troyanskiy/rest-core/blob/master/README.md)
