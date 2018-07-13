This folder contains clones of build repository from ckeditor.

#WHY DO WE NEED THIS?
1. You don't need these build to run sample. The sample loads the ckeditor from CDN directly.
However, if you need to dig into source code of ckeditor, it's much more convenient to rebuild the source code without uglificiation.

2. In order to add a plugins, we need to rebuild the ckeditor source. Adding a plugin to an existing build of ckeditor may crash or duplicate ckeditor core source code.
https://docs.ckeditor.com/ckeditor5/latest/builds/guides/development/installing-plugins.html

# SUB FOLDER CKEDITOR5-BUILD-CLASSIC
This folder is clone of https://github.com/ckeditor/ckeditor5-build-classic with modifications below:
- Add autosave plugin
  npm install --save-dev @ckeditor/ckeditor5-autosave
  Update src/ckeditor.js to add Autosave plugin
- In package.json: 
  Add builddev to build using development mode. This is optional, but it's useful for
  digging into ckeditor source code during development. Do not use this for productionN
- In src/ckeditor.js
  Add:
  ClassicEditor.build = ClassicEditor.build || {};
  ClassicEditor.build.config = ClassicEditor.defaultConfig;
  ClassicEditor.build.plugins = ClassicEditor.builtinPlugins;
  These configs are set by the prebuilt package but "somehow" they are not set commit into build repository
  

 