Mysteries of Auto Layout, Part 1

* Outline
  * Part 1
     * Maintainable Layouts
     * Changing Constraints
     * View Sizing
     * Self-Sizing Table View Cells
     * Priorities
     * Alignment
  * Part 2
     * The Layout Cycle
     * Legacy Layout
     * Constraint Creation
     * Constraining Negative Space 
     • Unsatisfiable Constraints
     * Resolving Ambiguity
* Maintainable Layouts - Mystery #1
* Constraints
  * Spacing and alignment
* Many Constraints
* Stack View - UIStackView (iOS 9) and NSStackView (OS X 10.9)
  * Built with Auto Layout
  * Manages constraints 
  * Horizontal or vertical
  * Alignment
  * Distribution
  * Animate
* Stack View in Interface Builder
  * Easy to build
  * Easy to maintain 
  * Composable Stack Views 
  * Lightweight
* Start with Stack View, use constraints as needed
* Feeding the Layout Engine
* Getting from Constraints to Layout
* Changing Constraints - Mystery #2
* Activate and Deactivate
  * Constraints find their own container 
  * Adds constraints efficiently
  * Do not need to own all views
* Things to Keep in Mind
  * Never deactivate self.view.constraints
     * Not all of those constraints belong to you Weird things will happen
     * Just don’t do it!
  * Keep references to constraints that change
* Changing Constraints
  * Never deactivate self.view.constraints 
  * Keep references to constraints
  * Animate changing constraints with view animation
* Building the Layout
* View Sizing - Mystery #3
* View Size - Intrinsic content size
  * Certain views have an intrinsicContentSize
￼￼   * For instance–labels and image views
  * Size derived from non-constraint internals 
  * System makes the size constraints
  * Layout size is not guaranteed
* View Size - Defining a particular view size
  * Use constraints first
  * Override intrinsicContentSize for specific reasons
     * If size information does not come from constraints 
     * If view has custom drawing (sometimes)
     * You will be responsible for invalidating
  * Size can change with size class changes
* Self-Sizing Table View Cells - Mystery #4
* Self-Sizing Table View Cells
  * Self-sizing needs size from constraints
  * Width is defined with table view cells
  * Constraints must determine height
     * Take advantage of proportions
* View Sizing
  * Certain views have an intrinsicContentSize 
  * Constraints should define size when possible
  * For self-sizing views, define size fully in constraints
* Building the Layout
* Priorities - Mystery #5
* Ambiguity - Why does it happen?
  * More than one layout solution
     * Not enough constraints 
     * Equal, non-required priorities
  * The engine makes a choice
* Constraint Priorities
  * Priorities go from 1–1000
  * Required is 1000
  * DefaultHigh is 750
  * DefaultLow is 250
  * Highest priority wins
  * System uses some priorities
     * Set around, not equal to
* Content Priorities
  * How a view handles its content
  * By default, these are not set as required
     * Do not set as required
     * Can cause unsatisfiable constraints
  * Equal priorities can cause ambiguity
  * Types
     * Content hugging 
     * Compression resistance
* Priorities
  * Can help keep constraints from unsatisfiability
     * But look out for competing priorities!
  * Results are more consistent
  * Use content priorities to get to the right layout
     * Hugging priorities hug content 
     * Compression resistance resists squishing
* Building the Layout
* Alignment - Mystery #6
* Aligning Baselines
  * Use firstBaseline and lastBaseline 
  * Aligns text better than top or bottom 
  * Better control over changing views
* Leading and Trailing
  * Use leading/trailing instead of left/right 
  * Helps with prep for localization
* Alignment Rects
  * Usually (not always) same as frame
  * Includes the critical content only
  * Does not change when view is transformed
  * Override alignmentRectInsets if needed
  * Find out the calculated rects
     * Use Show Alignment Rectangles  
     * Get using alignmentRectForFrame:
  * More in Part 2
* Alignment
  * First and last baseline for better aligned text
  * Leading and trailing instead of left and right
  * Override alignmentRectInsets to adjust alignment rects
* Summary
  * Stack Views help build easily maintainable layouts
  * Use activate and deactivate for constraints
  * Determine size through constraints
     * Override intrinsicContentSize judiciously
  * Use priorities to properly solve your layout
  * Alignment goes beyond top, bottom, and center
     * Keep localization in mind