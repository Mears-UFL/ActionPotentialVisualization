# ActionPotentialVisualization
A simplified, educational D3 animation of a neuron's dendritic voltage and cellular processes during the action potential event.

##Summary

This visualization is a graph of the voltages, in milliVolts, of a neuron at the Axon Hillock (the receiving end). It charts the voltages at the hillock over time; showing the 3 thresholds of voltage from stimulus to when the neuron is ready to fire again. The diagram below illustrates the cellular processes that take place before, during, and after a neuron reaches Action Potential at the Axon Hillock.

##Design

After a first project attempt at visualizing the Enron fraud data as a network proved a little too ambitious (go [here](https://github.com/Cascode6/EnronVisualization) to check it out), I decided to switch topics. I had wanted to create an animation of a neuron fire event since my neurobiology classes in college; so that is what I picked. 

My initial design for this illustration was based on line charts I memorized in college, showing the voltage levels across time. For this project, though, I settled on a bubble chart, with horizontal threshold lines at important steps in the life cycle of the axon hillock's polarity. I thought that these, combined with increasing scale and a color change, would indicate the most important steps in the process more clearly than a line chart, and would be easier to process quickly in conjunction with an animation of the neuron fire event.

For the initial neuron diagram, I took the bare bones from an image I designed using [http://editor.method.ac/](http://editor.method.ac/), (unaltered, generated code seen in [neurondiagrambase.html](https://github.com/Cascode6/ActionPotentialVisualization/blob/master/neurondiagrambase.html)). I imagined a click-through design, highlighting the time-based changes in the graph and the diagram, until action potential was reached. Then, like a real neuron, the event would be triggered, and the animation would play through the rest of the neuron fire event, and re-set itself.

My feedback was that the bubble chart and threshold lines conveyed the idea of steps in a process well (yay!), but the combination of click-through and animation was not ideal (boo). I took reviewer 2's advice and separated my functionality into one button for playing the animation as a slowed-down time sequence, and another for displaying the whole sequence - this allows the user to play with the neuron fire simply, and click-reveal-text the different symbols and states for more information. I attempted hover-reveal-text, but as these were some of the longest text segments in the display, I found it too spastic for absorbing the information. 

A Udacity review suggested that my initial design, a step-through-animation, deserved a little more attention. I also wanted to include more information about the voltage stages separate from the fire event, and streamline the display on all text updates. After being pointed to a [modelbox tutorial](http://www.w3schools.com/howto/howto_css_modals.asp), I updated the click events to slide up from the bottom - I especially liked this version, as it highlighted the text while leaving the visualization visible. For the chart, I combined a hover-zoom feature for readability with a click-reveal-text feature, to give the user complete control over how much and how long information is displayed.



First Version: [neuronindex1.html](https://github.com/Cascode6/ActionPotentialVisualization/blob/master/neuronindex1.html)

Feedback on [neuronindex1_5.html](https://github.com/Cascode6/ActionPotentialVisualization/blob/master/neuronindex1_5.html):

  "Graph should have axes, label, etc, and draw the lines at important neuron events (action potential, resting state) when you highlight a time index at that state, rather than having them there all the time. Label the line with the state name, and label the dots with the number to make it more readable. Also, make the dots bigger." - Reviewer 1
  
  "Make the neuron closer to the graph and slow the animation down - its hard to follow the graph change and the animation. And maybe use two buttons - one to play the animation, one to reveal all steps with some explanatory text?" - Reviewer 2

  "It's a little disjointed right now - if the voltage levels are related to the ions in the diagram, they should match. That would make the time-highlight in red a little less cartoonish. Also, move the numbers so we can still see them when the time bubbles change size." - Reviewer 3
  
These suggestions were all addressed in [neuronindex2.html](https://github.com/Cascode6/ActionPotentialVisualization/blob/master/neuronindex2.html). To accommodate the animation and the click-sensitivity features, I separated them into two additional JS files, and set up event handlers to call them in the main HTML file. I made the suggested color changes, arrangement changes and labeling changes, and insured that my graphics, title and text explanation would remain centered on the page. 

Feedback for [neuronindex2.html](https://github.com/Cascode6/ActionPotentialVisualization/blob/master/neuronindex2.html)
  "There’s a lot going on at the same time. This makes it difficult to focus and follow the “storyline”. - Udacity Review
  
Feedback for [neuronindex2_5.html](https://github.com/Cascode6/ActionPotentialVisualization/blob/master/neuronindex2_5.html)
  "It looks really pretty! So, how are the voltage levels and the neuron firing related again?" - Reviewer 4
  
These suggestions are taken into account in [neuronindex3.html](https://github.com/Cascode6/ActionPotentialVisualization/blob/master/neuronindex3.html). I reinstated the click-through to activation, and changed it so that all "bonus" informative text is contained in a modelbox that slides up from the bottom - for most browser arrangements, this will highlight the information, while still leaving the entire visualization visible (but darkened slightly). 

Resources used:   
my old notes from college on neuron anatomy and the action potential event
http://editor.method.ac/
http://www.w3schools.com/js/js_switch.asp  
https://bost.ocks.org/mike/transition/  
https://github.com/d3/d3-timer  
http://www.w3schools.com/js/js_timing.asp  
http://www.w3schools.com/js/tryit.asp?filename=tryjs_timing2  
https://bost.ocks.org/mike/bar/3/
http://alignedleft.com/ 
http://chimera.labs.oreilly.com/books/1230000000345/index.html (the whole book. all of it.)
