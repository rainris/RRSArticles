App Thinning in Xcode

* What You’ll Learn
  * How app distribution is being improved 
  * How to minimize your app’s footprint 
  * What this means for your workflow
* App Distribution Today
* What’s in an App?
  * Executable Code
     * 32-bit/64-bit
     * armv7/armv7s/arm64
  * Resources
     * Artwork Scale Factors - 1x/2x/3x
     * Artwork Device Idioms - iPad/iPhone
     * Graphics Technologies - OpenGL ES/Metal
     * Memory Classes - Low Quality/High Quality
     * Memory Classes - 96kb Audio/192kb Audio
     * Other Data
* App Slicing
  * iPad mini
     * armv7
     * 1x iPad
     * OpenGL ES Low Quality
     * 96kb Audio
     * Other Data
  * iPhone 6 Plus
     * arm64
     * 3x iPhone
     * Metal High Quality
     * 192kb Audio
     * Other Data
* Size Savings
* Can We Do Better?
  * Some things are always needed
     * Executable code
     * Basic interface and artwork
  * Other things may be needed only later
     * E.g., an advanced level in a game
  * Still other content might never been needed
     * E.g., a tutorial that the user watches only once
* On Demand Resources
  * Code
  * Images - Shared/Level 1/Level 2/Level 3 ...
  * Metal - Shared/Level 1/Level 2/Level 3 ...
  * Audio - Shared/Level 1/Level 2/Level 3 ...
  * Other - Shared/Level 1/Level 2/Level 3 ...
* On Demand Resources
  * Asset packs are built by Xcode
  * Can contain any non-executable assets Hosted by the App Store
  * Downloaded when needed
  * Reclaimed as appropriate
  * Device-thinned just like the other content  
* Advantages
  * Support devices with constrained storage
  * Shorter download times
  * Easier to stay within over-the-air size limits
  * Support more types of devices with less compromise 
  * Add features that couldn’t previously fit
* Asset Slicing
* How Does It Work?
  * Seamlessly integrated into build, export, and publish workflows
  * Post-processing of Asset Catalog and executable files
* What Do You Need to Do? 
  * You've probably already been doing it
     * 1x, 2x, 3x Artwork
  * Use Asset Catalogs
* Asset Catalogs
  * Asset Catalogs organize resources according to relevant device traits 
  * Note: Resources must be in an Asset Catalog to be eligible for thinning
* Device Traits
  * Devices have a key set of characteristics which assets can be optimized for
     * Screen resolution 
     * Device family
  * Graphics capabilities
     * Metal GPUFamily1, Metal GPUFamily2
  * Memory Level
     * 1GB,2GB
* Asset Catalog Content
* Named Images
  * Artwork resources for your application
     * PNG, JPG, and PDF formats
* Named Data
  * Store arbitrary file content
  * Classify according to hardware capabilities
  * Use NSDataAsset class to retrieve content in your application
* Sprite Atlases
  * Full SpriteKit integration
  * Automatic creation of SKTextureAtlases from image assets
  * Will be thinned appropriately
* Asset Catalogs to App Thinning
  * Each asset in the catalog has trait markup information
  * Traits used to route resources to relevant thinned app variants
* Asset Organization
  * Cataloging efficiently is key
  * Robust markup means less redundancy in sliced application variants 
  * Don’t leave assets as universal if they are only used on one device family
* Workflows
  * Create -> Build -> Distribute
* Xcode Asset Catalog Editor
* Asset Catalogs and External Toolchains
  * What if your team cannot use Xcode for asset production? 
  * Export image sets and data sets from existing asset pipelines 
  * XCAsset Source Artifact Format
  * Simple folder structure and JSON markup
* Image Sets
* Contents.json
  * Contains all asset markup information
  * Image Set Contents.json
  * Data Set Contents.json
* Example: Image Set Creation 
  * Hypothetical workflow using Photoshop CC Generator
* Integrating with Your Xcode Project
  * Project must have an xcasset folder reference
  * Place any externally generated content within xcasset folder 
  * No limitations on file hierarchy
* Build Workflow
  * Xcode Build and Run automatically thins resources for the active run destination 
  * Supported for all simulator and device run destinations 
  * ENABLE_ONLY_ACTIVE_RESOURCES target build setting
* Build Workflow
  * Speeds up iterative development
  * Test impact of cataloging changes on thinned outputs
* Distributing Thinned Applications
  * App Store Purchase
  * TestFlight
  * Ad-hoc/Enterprise Distribution 
  * Xcode Server
* Ad-hoc/Enterprise Distribution
  * Export for a specific device
  * Export thinned variants for all compatible devices
* Over-the-Air Installation
  * Save for Ad-Hoc/Enterprise with distribution manifest option
  * Xcode generates manifest plist containing URLs for each app variant
  * URLs are indexed by supported product type
  * Device automatically installs URL appropriate for its product type
* Xcode Server
  * Turnkey solution for building, hosting, and distributing thinned apps
  * All app variants built by Integration Bots
  * Point your device at the server web portal and go
  * Streamlined installation of thinned applications using over-the-air manifest
* What We’ve Seen
  * How app distribution is being improved 
  * How to minimize your app’s footprint 
  * What this means for your workflow
* What You Should Do
  * Create tailored versions of assets
  * Use Asset Catalogs to organize your assets 
  * Test your thinned app variants using Xcode 
  * Use Xcode Server to automate builds
  * Take advantage of On Demand Resources
