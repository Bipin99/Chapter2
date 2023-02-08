# Chapter2

 Q.What is `NPM`?
 ->
npm is the world's largest Software Registry.

The registry contains over 800,000 code packages.

Open-source developers use npm to share software.

Many organizations also use npm to manage private development.
 What are the uses of npm?
 NPM is used to manage dependencies for packages. If you were to unpack a framework and use it outside NPM, you would have to do this every
 time you want to update the framework.
 NPM does this for you. You always know what version you're on, and you can limit a dependency to a specific major/minor/patch version.

The npm i (or npm install) is used to install all dependencies or devDependencies from a package

Q.  What is `Parcel/Webpack`? Why do we need it?
ans=> parcel and webpack is a bundler. 
Parcel and webpack are the bundlers used mostly for JavaScript or Typescript code that helps you to minify, clean, and make your code
 compact so that it becomes easier to send
 a request or receive the response from the server when it usually takes you to transfer multiple files without using 
any bundler for loading the page of your application. Both of these bundlers substantially reduce the time it takes for
 the transfer of data and files to the server from the application. Along with that both bundlers parcel and webpack remove 
the unnecessary comments, new lines, any kind of block delimiters, and white spaces while the functionality of the code 
remains unchanged.

Q. What is `.parcel-cache`
-> 


The .cache folder (or .parcel-cache in parcel v2) stores information about your project when parcel
 builds it, so that when it rebuilds, it doesn't have to re-parse and re-analyze everything from scratch.
 It's a key reason why parcel can be so fast in development mode. I think committing it to git would be a
 bad idea - it would add a large number of (unnecessary)
 changes to your commit history, and it could easily get out-of-sync with the code that generated it.



Q. What is `npx` ?
ans-> NPX: The npx stands for Node Package Execute and it comes with the npm, when you installed npm above 5.2.0 version then automatically 
npx will installed. It is an npm package runner that can execute any package that you want from the 
npm registry without even installing that package. The npx is useful during a single time use package. 
If you have installed npm below 5.2.0 then npx is not installed in your system. You can check npx is installed 
or not by running the following command:


npx -v

Q. What is difference between `dependencies` vs `devDependencies`
ans-> Dependencies: In package.json file, there is an object called dependencies and it consists of all the packages that are used in the project with its version number. So, whenever you install any library that is required in your project that
 library you can find it in the dependencies object. 

Dev Dependencies: In package.json file, there is an object called as dev Dependencies and it consists of all the packages that are used in the project in its development phase and not in the production or testing environment with its version number. So, whenever you want to install any library that is required only in your development phase then you can find it in the dev Dependencies object. 

Use the below command to add more dev Dependencies in your project:

npm install <package name> --save-dev

Q. What is Tree Shaking?
ans->Tree shaking is a term used as a means to eliminate code that isn't in use, or dead-code, as we call it. You can also think of it like choosing 3-4 relevant quotes from a book to write an excellent paper. If you only need 3-4 relevant quotes, why use the entire book?

Whenever a code bundler, like webpack, builds our web application for production. It does tree shaking. Code bundlers like webpack do their best to remove dead code, or unused code, to reduce the bundle size of your application when you prepare your code to be able to be used for production. Unfortunately, it can't catch everything, and that because we sometimes write code that isn't tree shaking friendly.

A way for us to help code bundlers with tree shaking, or eliminating dead code, in our web development projects is to only import necessary methods and components into our application. We do this by using JavaScript destructuring syntax in our import statements and properly export code as well.


Q. What is Hot Module Replacement?


Hot Module Replacement (HMR) exchanges, adds, or removes modules while an application is running, without a full reload. This can significantly speed up development in a few ways:

Retain application state which is lost during a full reload.
Save valuable development time by only updating what's changed.
Instantly update the browser when modifications are made to CSS/JS in the source code, which is almost comparable to changing styles directly in the browser's dev tools.


Q.What is `.gitignore`? What should we add and not add into it?

ans-> When you’re working in your copy, Git watches every file in and considers it in three ways:

1.Tracked: You’ve already staged or committed the file.
2.Untracked: You’ve not staged or committed.
3.Ignored: You’ve explicitly told Git to ignore the file(s).
The .gitignore file tells Git which files to ignore when committing your project to the GitHub repository. gitignore is located in the root directory of your repo.

Q.What is the difference between `package.json` and `package-lock.json`

ans-> A package.json file contains metadata about the project and also the functional dependencies that is required by the application.
package.lock.json is created for locking the dependency with the installed version. It will install the exact latest version of that package in your application and save it in package.json. Let’s say if the current version of the package is 1.3.2 then it will save the version with (^) sign. Here carot(^) means, it will support any higher version with major version 1 for eg. 1.2.2.
Without package.lock.json, there might be some differences in installed versions in different environments. To overcome this problem, package.lock.json is created to have the same results in every environment. It should be in source control with the package.json file because if any other user will clone the project and install dependencies then it will install the exact same dependencies as in package.lock.json to avoid differences.

Q. Why should I not modify `package-lock.json`?
-> Package.json is the heart of every Nodejs Project. Understanding the role of package.json and how it relates to npm is an important part of developing Node.js apps, and increasingly an important part of the JavaScript ecosystem. 
Although `package.json` is automatically generated and updated by npm, it can also be edited manually. This allows you to change the metadata and npm module dependencies for your NodeJS project with ease. Package.json is not you Javascript object literal , it must be JSON as it’s name says.
In general, `package.json` doesn’t specify exact version numbers for dependencies (although it can if you want it to). Instead, `package.json` generally sets the minimum version for each dependency, and it can also set a range of versions. In addition, `package.json` only tracks top-level dependencies for the project. You don’t need to specify dependencies of dependencies; that’s handled automatically for you. This makes `package.json` smaller in size, more accurate, and much more human-readable.
The problem with `package.json` is that you and your vulnerability scanner can end up seeing different versions of dependencies. Yet worse, you could be running different versions compared to what is running in production. That’s because `package.json` usually doesn’t specify exact versions, so depending on when/where you invoke npm install, you can see different versions than a vulnerability scanner. This is a recipe for disaster and lots of unneeded work.
The `package-lock.json` file was introduced in npm version 5 to solve this problem. It is a generated file and is not designed to be manually edited. Its purpose is to track the entire tree of dependencies (including dependencies of dependencies) and the exact version of each dependency.
You should commit package-lock.json to your code repository. Sharing this file with teammates and the production environment is the best way to make sure that everyone has the same configuration for their copy of the project.

