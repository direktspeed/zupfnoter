# Handling google analytics

* Analytics ia applied for webserver-installation only, not for localhost nor desktop
* this is done by the method `javascript_include_analytics` which is defined in the related rake tasks.
* for localhost, the method is not defined, and therefore the template does not include the script

# build environments

## project documentation

* goto `30_source/ZSUPP_Tools`
* `rake`

## maintain the application

* goto `30_source/SRC_Zupfnoter/src`
* `rake`

## updating syntax highlighting

* goto your clone of the ace reporitory (../200_zupfnoter_external_components/ace)
* update the files as described in <http://ace.c9.io/#nav=higlighter>
* run  `node static.js --allow-save` .
* navigate to http://localhost:8888/tool/mode_creator.html
* perform necessary changes
* perform 

	node Makefile.dryice.js -nc -m full

* copy the contents of `200_zupfnoter_external_components/ace/build/src-min-noconflict` to 
`30_sources/SRC_Zupfnoter/vendor/ace`

# preparing a release

Zupfnoter uses gitflow http://nvie.com/posts/a-successful-git-branching-model/

Before preparing a release, everything that should go to this release shall be committed to the develop branch.

* Gitflow: Start new release
    Pattern: V_1.4.0_RC2
* adjust version.rb
* perform all the builds
	`rake build`
	`rake deploy`
* Gitflow: finish the release
* switch back to the development branch
* bump version in src/version.rb, add ".dev"

# building the desktop app

The desktop app is built based on node-webkit. The major steps to build it are described in

https://github.com/rogerwang/node-webkit/wiki/How-to-package-and-distribute-your-apps

Approach follows nodebob but uses rake to do this.

1. create the webapp
2. create zupfnoter.nw
3. create the binaries for windows and osx



