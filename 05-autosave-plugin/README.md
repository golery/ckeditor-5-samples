This sample illustrates:
- Build a custom ckeditor5 with plugin autosave
- How to use autosave plugin

# HOW TO BUILD CUSTOM CKEDITOR
In order to use the plugin, we need to build a custom ckeditor.
There are 2 ways:
1. Add ckeditor dependency to your project and pack it with other javascripts
2. Build ckeditor separately 

The 2nd method is a preferred way because we only have to built it once, which speed up the 
building process.

The process to build custom ckeditor
1. Checkout repository ckeditor-build-xxx (ex: ckeditor-build-classic)
2. npm install plugin
3. Modify src/ckeditor.js
   - import autosave plugin
   - add default configuration 
     ClassicEditor.build = ClassicEditor.build || {};
     ClassicEditor.build.config = ClassicEditor.defaultConfig;
     ClassicEditor.build.plugins = ClassicEditor.builtinPlugins;
4. npm run build
       

