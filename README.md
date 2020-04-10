# skunkworkx-gsi based on https://github.com/phhusson/treble_experimentations

Initializing Repository
-----------------------

Repo initialization :
    
    ## Releases Repo ##
    $ repo init -u https://github.com/skunkworkx-gsi/platform_manifest.git -b aosp-gsi

sync repo :

    $ repo sync --no-tags --no-clone-bundle
    
problems syncing? :

    $ repo sync --no-tags --no-clone-bundle --force-sync

Building
--------
treble build options explained:

      Usage: $ bash build-treble.sh options buildVariants blissBranch
      options: -c | --clean : Does make clean && make clobber and resets the treble device tree
               -s | --sync: Repo syncs the rom (clears out patches), then reapplies patches to needed repos
      
      buildVariants:  arm64_a_stock | arm64_ab_stock : Vanilla Rom
                      arm64_a_gapps | arm64_ab_gapps : Stock Rom with Gapps Built-in
                      arm64_a_foss | arm64_ab_foss : Stock Rom with Foss
                      arm64_a_go | arm64_ab_go : Stock Rom with Go-Gapps
     
      
      First you must sync with the new manifest changes:
      
		$ bash build-treble.sh -s
      
      After the sync is finished, you can build your release:
      
    $ bash build-treble.sh -c arm64_ab_gapps (to build arm 64bit for ab partitions with gapps built in)
