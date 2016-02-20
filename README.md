# Lambda Lang Ideas

## Implementation Decisions

For every single implementation decision, have a list of all of the possible techniques for solving the problem. For each technique:

* List all of the pros and cons next to it
* Have a voting system where users vote for which techniques they want implemented
    * Show the total of the vote weights
    * Sort the techniques from most to least vote weight
    * Each Users' vote weight should grow linearly
        * Based on their contributions at a specific (organic?) rate
        * This is an attempt to keep it right on the line where that the community doesn't become overpowered by the core devs and vice versa.
    * The goal for the voting system is to encourage diversity and discourage fragmentation at the same time - this will be an interesting experiment :)
* Show a Difficulty to Implement meter
* Performance pros and cons ranked by votes as well
* Once a designated test suite is passing, convert the implementation into a namespaced package
* Have some sort of labeling for \`core', \`extra', \`community', \`wild' etc. (sort of like Arch does with packages) indicating how stable the package is
* Make all of this available for viewing/interacting with on the web

* Lambda Lang itself should be exceedingly minimalistic - any time the user adds code that requires more functionality, download that functionality via the package manager
    * For example array functionality
    * If the user prefers a specific package, specify that at the level of scope relevant - see the Scoping section
    * Include a utility which prints the code listing which package is being used at each instance in a verbose way

## Scoping

In lieu of a global and a local namespace (in an attempt to avoid dynamic scope, or to change it at least) let's try out scope sharing
* Labels?
* Simpler is better
* (load)?
    * When code is loaded from somewhere within the ast, children from there are suddenly in scope of what was loaded

## The Three Delimiter Characters

* Inner separator pipe |
* Outer separators (call it unicorn delimiters?) e.g. \`stuff~
    * Tic to start tilde to close

## Versions and upgrading

* When enormous implementation decisions change, run the upgrade utility on your code
    * Walk through step by step as it makes recommendations for upgrading your code
    * Alternatively, run the utility on auto first to see if everything upgrades seamlessly and all of your tests pass (You do have tests, right?)
