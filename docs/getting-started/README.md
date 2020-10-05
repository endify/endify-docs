# Getting started
## Install
### Install using npx
`npx hello-endify`
### Install manually
1. `yarn install endify`
2. Create configuration file
## Run
Type `endify dev` in your console (or just `endify`)


## Configuration
First step you should make in order to make Endify work like you want is to specify config.
Create `Endify.vue` file on top of your directory with the following content:
```html

<!-- Frontend configuration -->
<script config="client">
  import App from './src/App.vue'
  export default {
    mainComponent: App
  }
</script>

<!-- Server configuration -->
<script config="server">
  export default (defaultConfig) => {
    return {
      port: defaultConfig.port + 1 //3000 -> 3001
    } 
  }
</script>

<!-- Webpack build configuration -->
<script config="build">
  export default {
    electronEnv: {
      API_HOST: ''
    }
  }
</script>
```