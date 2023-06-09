# Add file in Node Module

This is a simple React application that demonstrates how to add files in node modules folder in a React project.

## Getting Started

To get started, clone the repository and navigate to the project directory. Then, install the dependencies using the following command:

```
npm install
```

Once the dependencies are installed, you can start the application using the following command:

```
npm start
```

The application will then be available at `http://localhost:3000/`.

## How it Works

First, add the file in the `node_modules` folder wherever you want. For example, suppose I have a file named `myFile.js` and I have added it at this path `node_modules/function-bind/test/myFile.js`.

Then you need to install the `patch-package` package as a dev dependency by running the following command:

```
npm install --save-dev patch-package
```

Next you need to create a patch file for the package you want to patch. To do this, create a new folder called `patches` in the root of your project and then create a patch file inside it with the name `<packagename>+version.patch` For example, if you want to patch the `react-dom` version `16.14.0`, you would create a file named `patches/react-dom+16.14.0.patch` 

Then you need to open the `package.json` file and under the scripts remove the start attribute and replace it with the following code:

```
"scripts": {
"start": "patch-package && react-scripts start"
}
```

That's it now run your application once and then you can delete the `node_modules` folder. After that whenever you'll re-install the `node_modules` folder, your files will also be installed automatically and you do not need to add them again and again manually.

## Conclusion

That's it! Using this way, you only need to add your file once in the node_modules folder and then even after you delete the node_modules, your file will be automatically installed when you re-install it. 


