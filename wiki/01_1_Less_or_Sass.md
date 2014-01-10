##LESS or SASS? Both.

- [Install Node](#install-node)
- [Install Grunt](#install-grunt)
- [LESS setup](#less-setup)
- [SASS setup](#sass-setup)

**Frontsize** was written to help people develop consistent themes with preprocessor languages, that's why you can use both main preprocessor languages, we love both.

Next we'll see how to create a configuration with [Node.js][3] and [Grunt.js][5], valid for [LESS][1] and [SASS][2] with just some little difference.

#####Why Node and Grunt?

Using **Node** and **Grunt** is useful to automate the conversion from [LESS][1] or [SASS][2] to the final CSS file, with the **Shell** command `grunt watch` is possible to look for changes to files inside your preprocessor environment an then automatically export your CSS file.

This can be used for [LESS][1] and [SASS][2] in the same way.

###Install Node

This part on **Node** installation is not the only way to do it, and it's skips the `package.json` configuration which is not used here and force the developer to include the `node_modules` installation folder inside your project.

The easyest way to install [Node.js][3] is to download the executable file and run it. This should install also [NPM][4] console for **Node**.

For more details I've found very useful this nice tutorial of [George Ornbo][7] for Mac OSX.

###Install Grunt 

After **Node**, you can now install  [Grunt.js][5] module which depends on Node.

```
$ npm install -g grunt-cli
```

Now we've done the job with **Grunt** installation, we can set the environment for [LESS][1] and [SASS][2].

```
$ cd /path/to/project-folder
$ npm install grunt grunt-contrib-watch
```

This will create a `node_modules` folder inside your `project-folder` with the components needed for **Grunt** to work properly with [LESS][1] or [SASS][2].

###LESS setup

First we need to install [LESS][1] compiler on Node:

```
npm install -g less
```

Now we need to configure our `Grunt.js` file for [LESS][1] workflow, first we have to understand how the folder structure should be defined:

```
$ cd /path/to/project-folder
$ npm install grunt grunt-contrib-less grunt-contrib-sass grunt-contrib-watch
```

**LESS and Grunt folder structure**

```
project-folder
project-folder/path/to/css/frontsize-less
project-folder/Grunt.js
```

**Grunt.js configuration**

```javascript
module.exports = function(grunt) {
	grunt.initConfig({
		// running `grunt less` will compile once
		less: {
			development: {
				options: {
					compress: false,
					cleancss: false,
					rootpath: ""
				},
				files: {
					"./path/to/css/frontsize.css" : "./path/to/css/frontsize-less/compile.less"
				}
			},
			production: {
				options: {
					compress: true,
					cleancss: true,
					rootpath: ""
				},
				files: {
					"./path/to/css/frontsize.min.css" : "./path/to/css/frontsize-less/compile.less"
				}
			}
		},
		// running `grunt watch` will watch for changes
		watch: {
			files: [
				"./css/**/*.less"
			],
			tasks: [
				"less:production"
			]
		}
	});
	grunt.loadNpmTasks('grunt-contrib-less');
	grunt.loadNpmTasks('grunt-contrib-watch');
};
```

###SASS setup

Here we have basically the same configuration inside our `Grunt.js` file for [SASS][2] workflow, we have the same folder structure:

**LESS and Grunt folder structure**

```
project-folder
project-folder/path/to/css/frontsize-sass
project-folder/Grunt.js
```

**Grunt.js configuration**

```javascript
module.exports = function(grunt) {
	grunt.initConfig({
		// running `grunt sass` will compile once
		sass: {
			development: {
				options: {
					style: "expanded" // nested compact compressed expanded
				},
				files: {
					"./css/frontsize.css" : "./compile.scss"
				}
			},
			production: {
				options: {
					style: "compressed"
				},
				files: {
					"./css/frontsize.min.css" : "./compile.scss"
				}
			}
		},
		// running `grunt watch` will watch for changes
		watch: {
			files: [
				"./css/**/*.scss"
			],
			tasks: [
				"sass:development"
			]
		}
	});
	grunt.loadNpmTasks('grunt-contrib-sass');
	grunt.loadNpmTasks('grunt-contrib-watch');
};
```

The only differences are inside `options` element of the `Grunt.js` configuration.