How to load a 3D image with Three.js
===================================

The entire three.js library is huge, so in order make this goal more manageable I removed everything except what is needed for loading a collada image (a type of 3d image) into a website.

Options
-------


1. git clone onto your computer 
  * `git clone https://github.com/gskielian/Collada-Import-Three.js.git`

2. Downloading as a Zip File and editing locally

3. Getting your own github copy of this repo and editing directly on github;
  * Select `Fork` on the top right to get your own copy this repository and start modifying the [webgl_loader_collada.html](webgl_loader_collada.html).


Usage
-----

First find a collada format (.dae) 3D model (please let me know of good 3D model sites:smiley:):

http://sketchup.google.com/3dwarehouse/

Next, load the file into the directory `./Collada/models/[name of folder]/[name of file].dae`

Finally, change the following lines in the webgl_loader_collada.html file:

```javascript
loader.load( './models/collada/monster/monster.dae', function ( collada ) {

				dae = collada.scene;
				skin = collada.skins[ 0 ];

				dae.scale.x = dae.scale.y = dae.scale.z = 0.002;
				dae.updateMatrix();

				init();
				animate();

			} );
```
into
```javascript
loader.load( './models/collada/[name of folder]/[name of file].dae', function ( collada ) {

				dae = collada.scene;
				skin = collada.skins[ 0 ];

				dae.scale.x = dae.scale.y = dae.scale.z = 0.002;
				dae.updateMatrix();

				init();
				animate();

			} );
```
 

Viewing Your File:
------------------
If viewing does not work locally on your computer, try using method 3 and selecting the "raw" version of the webgl_loader_collada.html code, and deleting the period after raw and pressing enter: raw.github... -> rawgithub

Or simply click here*:  https://rawgithub.com/gskielian/Collada-Import-Three.js/master/webgl_loader_collada.html

(replace `gskielian` with your github username if using this from a forked-repository)

This should render your page in your browser.
