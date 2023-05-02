Download Link: https://assignmentchef.com/product/solved-cmpt381-assignment-3-model-view-controller
<br>
In this assignment, you will demonstrate your skills in developing applications that use the Model-View-Controller pattern, and that handle touch interaction and immediate-mode graphics using the Android platform. You will develop a simple graph editor with multiple views, where the user can interactively add to and manipulate vertices and edges in the graph.

Part 1: A Basic Android Graph Editor

Build a simple GUI in Android that allows the user to create and manipulate a graph.

Interface requirements:

<ul>

 <li>A main panel that fills the screen (but does not scroll)</li>

 <li>The main panel is the area where the user will interact with the graph (see below)</li>

 <li>The main panel shows all graph vertices, labels, and edges Interaction requirements:</li>

 <li>Touching and releasing on the background of the main panel creates a new vertex, drawn as a blue circle with an integer label (V0, V1, etc.)</li>

 <li>Touching down on an existing vertex selects that vertex (shown by drawing the vertex in orange); dragging then moves the vertex (including any associated edges). Releasing the touch returns the vertex to blue</li>

 <li>If the user long-presses on a vertex, the orange circle gets a black border, and when the user drags their finger, a temporary edge is drawn to their finger location. If the user releases the touch on another vertex, the edge is added to the graph (if the user releases on the background, the edge is discarded).</li>

</ul>

Software requirements:

<ul>

 <li>You must implement the system using Model-View-Controller, with correct separation between these components</li>

 <li>Create separate classes for the Model, the View, and the Controller, following the examples given in class</li>

 <li>Create a class for the InteractionModel to store the selection and the coordinates of the temporary edge</li>

 <li>Implement publish-subscribe communication to notify Views of changes to the Model and to the InteractionModel  Build the system using the following classes:</li>

</ul>

o              MainActivity o                 GraphModel o                 Vertex o                 Edge o                 InteractionModel o                 MainGraphView o       MainGraphViewController

Resources for part 1:

<ul>

 <li>Custom Views in Android: <u>https://developer.android.com/training/custom-views/index.html</u></li>

 <li>Custom drawing: <u>https://developer.android.com/training/custom-views/custom-drawing</u></li>

 <li>Attaching events to custom views: <u>https://developer.android.com/training/custom-views/making-interactive</u></li>

</ul>

<h1>Part 2: Two Views and View Navigation</h1>

In the second part of the assignment you will extend your system from part 1 to add another view (a mini view), and to enlarge the main view so that view navigation (i.e., swiping to move the viewport) is possible.

Additional interface requirements:

<ul>

 <li>The main panel is now 3000×3000 pixels in size, meaning that it is not all shown at once on the screen.</li>

 <li>There is now a second view (the mini view) at the top of the screen. The mini view shows a miniature version of the entire 3000×3000 main view. The mini view shows all vertices and edges, selection colour changes, and the temporary edge, but does not show vertex labels.</li>

 <li>The mini view can be any square size (specified when adding the view to the layout)</li>

 <li>The mini view also shows a grey viewfinder rectangle that indicates the extents of the main view within its 3000×3000 area. The viewfinder moves as the user swipes to change the location of the main view (see below).</li>

 <li>The white space to the right of the mini view is not used. Additional interaction requirements:</li>

 <li>Touching and dragging on the main view’s background now moves the main view to a new location in the 3000×3000 area.</li>

 <li>The main view’s location and size within the 3000×3000 area is stored in the InteractionModel</li>

 <li>All manipulations of vertices and edges are the same as described above.</li>

</ul>

Additional software requirements:

<ul>

 <li>The mini view should use the existing publish-subscribe mechanism to receive notifications about model changes; in addition, the mini view will need to communicate with the InteractionModel in order to determine the extents of the viewport.</li>

 <li>Add one class for the new view: MiniGraphView</li>

 <li>When adding the mini view to the screen layout, the programmer can set any square size for the view using the LayoutParams argument to the layout’s addView() method. For example:</li>

</ul>

o    vertical.addView(miniView,new LinearLayout.LayoutParams(400,400));

<ul>

 <li>Your controller must implement a state machine (as introduced in class) to determine what actions to take at what times (e.g., whether a move implies a swipe of the viewport, a move of a vertex, or drawing a temporary edge).</li>

</ul>

This assignment is to be completed individually; each student will hand in an assignment.