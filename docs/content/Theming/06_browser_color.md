@ngdoc content
@name Browser Colors
@description
## This feature is **mobile** only

![browser color](https://cloud.githubusercontent.com/assets/6004537/18006666/50519c7e-6ba9-11e6-905b-c3751c20549c.png)

Enables browser header coloring with [Material Design Colors](https://material.google.com/style/color.html) and the theming system, <br/> 
for more info please visit [here](https://developers.google.com/web/fundamentals/design-and-ui/browser-customization/theme-color)
 
## Usage
### Config phase
<hljs lang="js">
  myAppModule
    .config(function($mdThemingProvider) {
      // Enable browser color
      $mdThemingProvider.enableBrowserColor({
        theme: 'myTheme', // Default is 'default'
        palette: 'accent', // Default is 'primary', any basic material palette and extended palettes are available
        hue: '200' // Default is '800'
      });
    });
</hljs>

### Runtime
<hljs lang="js">
  myAppModule
    .controller('myCtrl', function($scope, $mdTheming) {
      var removeFunction = $mdTheming.setBrowserColor({
        theme: 'myTheme', // Default is 'default'
        palette: 'accent', // Default is 'primary', any basic material palette and extended palettes are available
        hue: '200' // Default is '800'
      });
      
      $scope.$on('$destroy', function () {
        removeFunction(); // COMPLETELY removes the browser color
      })
    })
</hljs>

Options parameter: <br/>
`theme`   - A defined theme via `$mdThemeProvider` to use the palettes from. Default is `default` theme. <br/>
`palette` - Can be any one of the basic material design palettes, extended defined palettes and 'primary',
            'accent', 'background' and 'warn'. Default is `primary`. <br/>
`hue`     - The hue from the selected palette. Default is `800`<br/>

