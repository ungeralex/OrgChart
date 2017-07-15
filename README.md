![OrgChart](http://dabeng.github.io/OrgChart/img/orgchart-heading.png)

# [Perhaps you'd prefer the native javascript(ES6) version](http://github.com/dabeng/OrgChart.js)
# [Perhaps you'd prefer the Web Components version](http://github.com/dabeng/OrgChart-Webcomponents)

## Foreword
- First of all, thanks a lot for [wesnolte](https://github.com/wesnolte)'s great work:blush: -- [jOrgChart](https://github.com/wesnolte/jOrgChart). The thought that using nested tables to build out the tree-like orgonization chart is amazing. This idea is more simple and direct than its counterparts based on svg
- Unfortunately, it's long time not to see the update of jOrgChart. on the other hand, I got some interesting ideas to add, so I choose to create a new repo.
- Font Awesome provides us with administration icon, second level menu icon and loading spinner.

## Features
- Supports both local data and remote data (JSON).
- Smooth expand/collapse effects based on CSS3 transitions.
- Align the chart in 4 orientations.
- Allows user to change orgchart structure by drag/drop nodes.
- Allows user to edit orgchart dynamically and save the final hierarchy as a JSON object.
- Supports exporting chart as a picture or pdf document.
- Supports pan and zoom
- Users can adopt multiple solutions to build up a huge organization chart(please refer to multiple-layers or hybrid layout sections)
- touch-enabled plugin for mobile divice

## Installation
Of course, you can directly use the standalone build by including dist/js/jquery.orgchart.js and dist/css/jquery.orgchart.css in your webapps.
### Install with Bower
```
# From version 1.0.2 on, users can install orgchart and add it to bower.json dependencies
$ bower install orgchart
```

### Install with npm
```
# From version 1.0.4 on, users can install orgchart with npm
$ npm install orgchart
```
require('orgchart') will load orgchart plugin onto the jQuery object. The orgchart module itself does not export anything.

## [Demo](http://dabeng.github.io/OrgChart/)
- **[using ul datasource](http://dabeng.github.io/OrgChart/ul-datasource/)**(this feature comes from [Tobyee's good idea:blush:](https://github.com/dabeng/OrgChart/issues/1))

![ul datasource](http://dabeng.github.io/OrgChart/ul-datasource/snapshot.png)

- **[using local datasource](http://dabeng.github.io/OrgChart/local-datasource/)**

![local datasource](http://dabeng.github.io/OrgChart/local-datasource/recorder.gif)

- **[I wanna pan&zoom the orgchart](http://dabeng.github.io/OrgChart/pan-zoom/)**

![pan & zoom](http://dabeng.github.io/OrgChart/pan-zoom/recorder.gif)

- **I wanna align orgchart with different orientation**(this feature comes from [the good idea of fvlima and badulesia :blush:](https://github.com/dabeng/OrgChart/issues/5))

  Top to Bottom -- default direction, as you can see all other examples on this page.

  [Bottom to Top](http://dabeng.github.io/OrgChart/direction/bottom2top)

![Bottom to Top](http://dabeng.github.io/OrgChart/direction/b2t.png)

  [Left to Right](http://dabeng.github.io/OrgChart/direction/left2right)

![Left to Right](http://dabeng.github.io/OrgChart/direction/l2r.png)

  [Right to Left](http://dabeng.github.io/OrgChart/direction/right2left)

![Right to Left](http://dabeng.github.io/OrgChart/direction/r2l.png)

- **[I wanna show/hide left/right sibling nodes respectively by clicking left/right arrow](http://dabeng.github.io/OrgChart/toggle-sibs-resp/)**

![toggle siblings respectively](http://dabeng.github.io/OrgChart/toggle-sibs-resp/recorder.gif)

- **[I wanna load datasource through ajax](http://dabeng.github.io/OrgChart/ajax-datasource/)**

![ajax datasource](http://dabeng.github.io/OrgChart/ajax-datasource/recorder.gif)

- **[I wanna load data on-demand](http://dabeng.github.io/OrgChart/ondemand-loading-data/)**

Note: when users use ajaxURL option to build orghchart, they must use json datasource(both local and remote are OK) and set the relationship property of datasource by themselves. All of these staff are used to generate the correct expanding/collapsing arrows for nodes.

![on-demand loading data](http://dabeng.github.io/OrgChart/ondemand-loading-data/recorder.gif)

- **[I wanna customize the structure of node](http://dabeng.github.io/OrgChart/option-createNode/)**

![option--createNode](http://dabeng.github.io/OrgChart/option-createNode/recorder.gif)

- **[I wanna export the organization chart as a picture](http://dabeng.github.io/OrgChart/export-orgchart/)**

Here, we need the help from [html2canvas](https://github.com/niklasvh/html2canvas).

![export orgchart](http://dabeng.github.io/OrgChart/export-orgchart/recorder.gif)

Besides, if you wanna export a pdf format, you need to introduce jspdf as shown bellow:
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/1.3.2/jspdf.debug.js"></script>
```

**Note:**

(1) if you wanna export something in IE or Edge, please introduce [es6-promise.auto.js](https://github.com/stefanpenner/es6-promise) firstly.

(2) if your OS is windows, please check your display scaling settings. For the perfact exported picture, you'd better adjust "Change the size of text, apps, and other items" to 100%.(thanks for [sayamkrai](https://github.com/sayamkrai)'s [exploration](https://github.com/dabeng/OrgChart/issues/152))

- **[I wanna itegrate organization chart with geographic information](http://dabeng.github.io/OrgChart/integrate-map/)**

Here, we fall back on [OpenLayers](https://github.com/openlayers/ol3). It's the most aewsome open-source js library for Web GIS you sholdn't miss.

![integrate map](http://dabeng.github.io/OrgChart/integrate-map/recorder.gif)

- **[I wanna edit orgchart](http://dabeng.github.io/OrgChart/edit-orgchart/)**

With the help of exposed core methods(addParent(), addSiblings(), addChildren(), removeNodes()) of orgchart plugin, we can finish this task easily.

![edit orgchart](http://dabeng.github.io/OrgChart/edit-orgchart/recorder.gif)

- **[I wanna drag & drop the nodes of orgchart](http://dabeng.github.io/OrgChart/drag-drop/)**

Users are allowed to drag & drop the nodes of orgchart when option "draggable" is assigned to true(**Note**: this feature doesn't work on IE due to its poor support for HTML5 drag & drop API).

![drag & drop](http://dabeng.github.io/OrgChart/drag-drop/recorder.gif)

Furthermore, users can make use of option dropCriteria to inject their custom limitations on drag & drop. As shown below, we don't want an manager employee to be under a engineer under no circumstance.

- **[I want a method that can decribe the hierarchy of orgchart](http://dabeng.github.io/OrgChart/get-hierarchy/)**

That's where getHierarchy() comes in.

![get hierarchy](http://dabeng.github.io/OrgChart/get-hierarchy/snapshot.png)

- **[I want a color-coded chart](http://dabeng.github.io/OrgChart/color-coded/)**

It's a so easy task, we just need to append id or className property to node data.

![color coded](http://dabeng.github.io/OrgChart/color-coded/snapshot.png)

- **[I want a multiple-layers chart](http://dabeng.github.io/OrgChart/multiple-layers/)**

In fact, this is a wonderful solution to display a orgchart which includes a huge number of node data.

![multiple layers](http://dabeng.github.io/OrgChart/multiple-layers/recorder.gif)

- **[I want a hybrid(horizontal + vertical) chart](http://dabeng.github.io/OrgChart/vertical-depth/)**

This feature is inspired by the issues([Aligning Children Vertical](https://github.com/dabeng/OrgChart/issues/46), [Hybrid(horizontal + vertical) OrgChart](https://github.com/dabeng/OrgChart/issues/61)). Thank [mfahadi](https://github.com/mfahadi) and [Destructrix](https://github.com/Destructrix) for their constructive suggestions:blush: Special thanks to [tedliang](https://github.com/tedliang) for his wonderful hybrid mode solution.

From now on, users never have to worry about how to align a huge of nodes in one screen of browser. The option "verticalDepth" allows users to align child nodes vertically from the given depth.

**Note**: currently, this option is incompatible with many other options or methods, like direction, drag&drop, addChildren(), removeNodes(), getHierarchy() and so on. These conflicts will be solved one by one in the later versions.

![hybrid layout](http://dabeng.github.io/OrgChart/vertical-depth/snapshot.png)

- **[I want to collapse some nodes by default](http://dabeng.github.io/OrgChart/default-collapsed/)**

No problem. You just need to adjust a little detail of datasource with the help of option "collapse" and className "slide-up".

- **[I want to refresh orgchart base on new options or datasource](http://dabeng.github.io/OrgChart/reload-data/)**

It's not a big deal. You just turn to the method init().

- **[I want to use complex template to customize the internal structure of every node](http://dabeng.github.io/OrgChart/custom-template/)**

No problem. With the help of ES6 Template literals, we can customize the any complex node structure rather than the common title and content sections.

![custom template](http://dabeng.github.io/OrgChart/custom-template/snapshot.png)

## Usage

### Instantiation Statement
```js
var oc = $('#chartContainerId').orgchart(options);
```

### Structure of Datasource
```js
{
  'id': 'rootNode', // It's a optional property which will be used as id attribute of node
  // and data-parent attribute, which contains the id of the parent node
  'collapsed': true, // By default, the children nodes of current node is hidden.
  'className': 'top-level', // It's a optional property which will be used as className attribute of node.
  'nodeTitlePro': 'Lao Lao',
  'nodeContentPro': 'general manager',
  'relationship': relationshipValue, // Note: when you activate ondemand loading nodes feature,
  // you should use json datsource (local or remote) and set this property.
  // This property implies that whether this node has parent node, siblings nodes or children nodes.
  // relationshipValue is a string composed of three "0/1" identifier.
  // First character stands for wether current node has parent node;
  // Scond character stands for wether current node has siblings nodes;
  // Third character stands for wether current node has children node.
  'children': [ // The property stands for nested nodes. "children" is just default name you can override.
    { 'nodeTitlePro': 'Bo Miao', 'nodeContentPro': 'department manager', 'relationship': '110' },
    { 'nodeTitlePro': 'Su Miao', 'nodeContentPro': 'department manager', 'relationship': '111',
      'children': [
        { 'nodeTitlePro': 'Tie Hua', 'nodeContentPro': 'senior engineer', 'relationship': '110' },
        { 'nodeTitlePro': 'Hei Hei', 'nodeContentPro': 'senior engineer', 'relationship': '110' }
      ]
    },
    { 'nodeTitlePro': 'Yu Jie', 'nodeContentPro': 'department manager', 'relationship': '110' }
  ],
  'otherPro': anyValue
};
```

### Options
<table>
  <thead>
    <tr><th>Name</th><th>Type</th><th>Required</th><th>Default</th><th>Description</th></tr>
  </thead>
  <tbody>
    <tr>
      <td>data</td><td>json or string</td><td>yes</td><td></td><td>datasource usded to build out structure of orgchart. It could be a json object or a string containing the URL to which the ajax request is sent.</td>
    </tr>
    <tr>
      <td>pan</td><td>boolean</td><td>no</td><td>false</td><td>Users could pan the orgchart by mouse drag&drop if they enable this option.</td>
    </tr>
    <tr>
      <td>zoom</td><td>boolean</td><td>no</td><td>false</td><td>Users could zoomin/zoomout the orgchart by mouse wheel if they enable this option.</td>
    </tr>
    <tr>
      <td>zoominLimit</td><td>number</td><td>no</td><td>7</td><td>Users are allowed to set a zoom-in limit.</td>
    </tr>
    <tr>
      <td>zoomoutLimit</td><td>number</td><td>no</td><td>0.5</td><td>Users are allowed to set a zoom-out limit.</td>
    </tr>
    <tr>
      <td>direction</td><td>string</td><td>no</td><td>"t2b"</td><td>The available values are t2b(implies "top to bottom", it's default value), b2t(implies "bottom to top"), l2r(implies "left to right"), r2l(implies "right to left").</td>
    </tr>
    <tr>
      <td>verticalDepth</td><td>integer</td><td>no</td><td></td><td>Users can make use of this option to align the nodes vertically from the specified depth.</td>
    </tr>
    <tr>
      <td>toggleSiblingsResp</td><td>boolean</td><td>no</td><td>false</td><td>Once enable this option, users can show/hide left/right sibling nodes respectively by clicking left/right arrow.</td>
    </tr>
    <tr>
      <td>ajaxURL</td><td>json</td><td>no</td><td></td><td>It inclueds four properites -- parent, children, siblings, families(ask for parent node and siblings nodes). As their names imply, different propety provides the URL to which ajax request for different nodes is sent.</td>
    </tr>
    <tr>
      <td>depth</td><td>positive integer</td><td>no</td><td>999</td><td>It indicates the level that at the very beginning orgchart is expanded to.</td>
    </tr>
    <tr>
      <td>nodeTitle</td><td>string</td><td>no</td><td>"name"</td><td>It sets one property of datasource as text content of title section of orgchart node. In fact, users can create a simple orghcart with only nodeTitle option.</td>
    </tr>
    <tr>
      <td>parentNodeSymbol</td><td>string</td><td>no</td><td>"fa-users"</td><td>Using font awesome icon to imply that the node has child nodes.</td>
    </tr>
    <tr>
      <td>nodeContent</td><td>string</td><td>no</td><td></td><td>It sets one property of datasource as text content of content section of orgchart node.</td>
    </tr>
    <tr>
      <td>nodeId</td><td>string</td><td>no</td><td>"id"</td><td>It sets one property of datasource as unique identifier of every orgchart node.</td>
    </tr>
    <tr>
      <td>createNode</td><td>function</td><td>no</td><td></td><td>It's a callback function used to customize every orgchart node. It recieves two parament: "$node" stands for jquery object of single node div; "data" stands for datasource of single node.</td>
    </tr>
    <tr>
      <td>exportButton</td><td>boolean</td><td>no</td><td>false</td><td>It enable the export button for orgchart.</td>
    </tr>
    <tr>
      <td>exportFilename</td><td>string</td><td>no</td><td>"Orgchart"</td><td>It's filename when you export current orgchart as a picture.</td>
    </tr>
    <tr>
      <td>exportFileextension</td><td>string</td><td>no</td><td>"png"</td><td>Available values are png and pdf.</td>
    </tr>
    <tr>
      <td>chartClass</td><td>string</td><td>no</td><td>""</td><td>when you wanna instantiate multiple orgcharts on one page, you should add diffent classname to them in order to distinguish them.</td>
    </tr>
    <tr>
      <td>draggable</td><td>boolean</td><td>no</td><td>false</td><td>Users can drag & drop the nodes of orgchart if they enable this option. **Note**: this feature doesn't work on IE due to its poor support for HTML5 drag & drop API.</td>
    </tr>
    <tr>
      <td>dropCriteria</td><td>function</td><td>no</td><td></td><td>Users can construct their own criteria to limit the relationships between dragged node and drop zone. Furtherly, this function accept three arguments(draggedNode, dragZone, dropZone) and just only return boolen values.</td>
    </tr>
    <tr>
      <td>initCompleted</td><td>function</td><td>no</td><td></td><td>It can often be useful to know when your table has fully been initialised, data loaded and rendered, particularly when using an ajax data source. It recieves one parament: "$chart" stands for jquery object of initialised chart.</td>
    </tr>
  </tbody>
</table>

### Methods
I'm sure that you can grasp the key points of the methods below after you try out demo -- [edit orgchart](http://dabeng.github.io/OrgChart/edit-orgchart/).

#### var oc = $container.orgchart(options)
Embeds an organization chart in designated container. Accepts an options object and you can go through the "options" section to find which options are required. Variable oc is the instance of class OrgChart.
#### init(newOptions)
It's the useful way when users want to re-initialize or refresh orgchart based on new options or reload new data.
#### addParent(data, opts)
Adds parent node(actullay it's always root node) for current orgchart.
<table>
  <thead>
    <tr><th>Name</th><th>Type</th><th>Required</th><th>Default</th><th>Description</th></tr>
  </thead>
  <tbody>
    <tr><td>data</td><td>json object</td><td>yes</td><td></td><td>datasource for building root node</td></tr>
    <tr><td>opts</td><td>json object</td><td>no</td><td>initial options of current orgchart</td><td>options used for overriding initial options</td></tr>
  </tbody>
</table>

#### addSiblings($node, data, opts)
Adds sibling nodes for designated node.
<table>
  <thead>
    <tr><th>Name</th><th>Type</th><th>Required</th><th>Default</th><th>Description</th></tr>
  </thead>
  <tbody>
    <tr><td>$node</td><td>jquery object</td><td>yes</td><td></td><td>we'll add sibling nodes based on this node</td></tr>
    <tr><td>data</td><td>json object</td><td>yes</td><td></td><td>datasource for building sibling nodes</td></tr>
    <tr><td>opts</td><td>json object</td><td>no</td><td>initial options of current orgchart</td><td>options used for overriding initial options</td></tr>
  </tbody>
</table>

#### addChildren($node, data, opts）
Adds child nodes for designed node.
<table>
  <thead>
    <tr><th>Name</th><th>Type</th><th>Required</th><th>Default</th><th>Description</th></tr>
  </thead>
  <tbody>
    <tr><td>$node</td><td>jquery object</td><td>yes</td><td></td><td>we'll add child nodes based on this node</td></tr>
    <tr><td>data</td><td>json object</td><td>yes</td><td></td><td>datasource for building child nodes</td></tr>
    <tr><td>opts</td><td>json object</td><td>no</td><td>initial options of current orgchart</td><td>options used for overriding initial options</td></tr>
  </tbody>
</table>

#### removeNodes($node）
Removes the designated node and its descedant nodes.
<table>
  <thead>
    <tr><th>Name</th><th>Type</th><th>Required</th><th>Default</th><th>Description</th></tr>
  </thead>
  <tbody>
    <tr><td>$node</td><td>jquery object</td><td>yes</td><td></td><td>node to be removed</td></tr>
  </tbody>
</table>

#### getHierarchy()
This method is designed to get the hierarchy relationships of orgchart for further processing. For example, after editing the orgchart, you could send the returned value of this method to server-side and save the new state of orghcart.

#### hideParent($node)
This method allows you to hide programatically the parent node of any specific node(.node element), if it has
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Required</th>
    <th>Default</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>$node</td>
    <td>JQuery Object</td>
    <td>Yes</td>
    <td>None</td>
    <td>It's the desired JQuery Object to hide its parent node. Of course, its sibling nodes will be hidden at the same time</td>
  </tr>
</table>

#### showParent($node)
This method allows you to show programatically the parent node of any specific node(.node element), if it has
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Required</th>
    <th>Default</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>$node</td>
    <td>JQuery Object</td>
    <td>Yes</td>
    <td>None</td>
    <td>It's the desired JQuery Object to show its parent node</td>
  </tr>
</table>

#### hideChildren($node)
This method allows you to hide programatically the children of any specific node(.node element), if it has
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Required</th>
    <th>Default</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>$node</td>
    <td>JQuery Object</td>
    <td>Yes</td>
    <td>None</td>
    <td>It's the desired JQuery Object to hide its children nodes</td>
  </tr>
</table>

#### showChildren($node)
This method allows you to show programatically the children of any specific node(.node element), if it has
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Required</th>
    <th>Default</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>$node</td>
    <td>JQuery Object</td>
    <td>Yes</td>
    <td>None</td>
    <td>It's the desired JQuery Object to show its children nodes</td>
  </tr>
</table>

#### hideSiblings($node, direction)
This method allows you to hide programatically the siblings of any specific node(.node element), if it has
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Required</th>
    <th>Default</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>$node</td>
    <td>JQuery Object</td>
    <td>Yes</td>
    <td>None</td>
    <td>It's the desired JQuery Object to hide its siblings nodes</td>
  </tr>
  <tr>
    <td>direction</td>
    <td>string</td>
    <td>No</td>
    <td>None</td>
    <td>Possible values:"left","rigth". Specifies if hide the siblings at left or rigth. If not defined hide both of them.</td>
  </tr>
</table>

#### showSiblings($node, direction)
This method allows you to show programatically the siblings of any specific node(.node element), if it has
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Required</th>
    <th>Default</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>$node</td>
    <td>JQuery Object</td>
    <td>Yes</td>
    <td>None</td>
    <td>It's the desired JQuery Object to show its siblings nodes</td>
  </tr>
  <tr>
    <td>direction</td>
    <td>string</td>
    <td>No</td>
    <td>None</td>
    <td>Possible values:"left","rigth". Specifies if hide the siblings at left or rigth. If not defined hide both of them.</td>
  </tr>
</table>

#### getNodeState($node, relation)
This method returns you the display state of related node of the specified node.
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Required</th>
    <th>Default</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>$node</td>
    <td>JQuery Object</td>
    <td>Yes</td>
    <td>None</td>
    <td>It's the desired JQuery Object to know its related nodes' display state.</td>
  </tr>
  <tr>
    <td>relation</td>
    <td>String</td>
    <td>Yes</td>
    <td>None</td>
    <td>Possible values: "parent", "children" and "siblings". Specifies the desired relation to return.</td>
  </tr>
</table>

The returning object will have the following structure:
```js
{
  "exist": true|false,  //Indicates if has parent|children|siblings
  "visible":true|false,  //Indicates if the relationship nodes are visible
}
```

#### getRelatedNodes($node, relation)
This method returns you the nodes related to the specified node
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Required</th>
    <th>Default</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>$node</td>
    <td>JQuery Object</td>
    <td>Yes</td>
    <td>None</td>
    <td>It's the desired JQuery Object to know its related nodes</td>
  </tr>
  <tr>
    <td>relation</td>
    <td>String</td>
    <td>Yes</td>
    <td>None</td>
    <td>Possible values: "parent", "children" and "siblings". Specifies the desired relation to return.</td>
  </tr>
</table>

#### setChartScale($chart, newScale)
This method returns you the nodes related to the specified node
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Required</th>
    <th>Default</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>$chart</td>
    <td>JQuery Object</td>
    <td>Yes</td>
    <td>None</td>
    <td>It's a chart in your chart-container</td>
  </tr>
  <tr>
    <td>newScale</td>
    <td>Float</td>
    <td>Yes</td>
    <td>None</td>
    <td>Positive float value which is used to zoom in/out the chart</td>
  </tr>
</table>

### Events
<table>
  <thead>
    <tr><th>Event Type</th><th>Attached Data</th><th>Description</th></tr>
  </thead>
  <tbody>
    <tr><td>nodedropped.orgchart</td><td>draggedNode, dragZone, dropZone</td><td>The event's handler is where you can place your customized function after node drop over. For more details, please refer to <a target="_blank" href="http://dabeng.github.io/OrgChart/drag-drop/">example drag & drop</a>.</td></tr>
    <tr><td>init.orgchart</td><td>chart</td><td>Initialisation complete event - fired when Organization Chart has been fully initialised and data loaded.</td></tr>
  </tbody>
</table>

### Tips
**How can I deactivate expand/collapse feature of orgchart?**

This use case is inspired by the [issue](https://github.com/dabeng/OrgChart/issues/25). Thanks [der-robert](https://github.com/der-robert) and [ActiveScottShaw](https://github.com/ActiveScottShaw) for their constructive discussions:blush:

Users can enable/disable exapand/collapse feature with className "noncollapsable" as shown below.
```js
$('.orgchart').addClass('noncollapsable'); // deactivate

$('.orgchart').removeClass('noncollapsable'); // activate
```

**How can I search nodes and show the minimized chart?**

This use case is inspired by the [issue](https://github.com/dabeng/OrgChart/issues/78). Thanks [Mmannem](https://github.com/Mmannem) for his constructive discussions:blush:
The following statements show the core logic and this is the complete [demo - filter node](http://dabeng.github.io/OrgChart/filter-node).
```js
var $chart = $('.orgchart');
// disalbe the expand/collapse feture
$chart.addClass('noncollapsable');
// distinguish the matched nodes and the unmatched nodes according to the given key word
$chart.find('.node').filter(function(index, node) {
    return $(node).text().toLowerCase().indexOf(keyWord) > -1;
  }).addClass('matched')
  .closest('table').parents('table').find('tr:first').find('.node').addClass('retained');
// hide the unmatched nodes
$chart.find('.matched,.retained').each(function(index, node) {
  var $unmatched = $(node).closest('table').parent().siblings().find('.node:first:not(.matched,.retained)')
    .closest('table').parent().addClass('hidden');
  $unmatched.parent().prev().children().slice(1, $unmatched.length * 2 + 1).addClass('hidden');
});
// hide the redundant descendant nodes of the matched nodes
$chart.find('.matched').each(function(index, node) {
  if (!$(node).closest('tr').siblings(':last').find('.matched').length) {
    $(node).closest('tr').siblings().addClass('hidden');
  }
});
```

**Why is the root node gone?**

When I have a huge orgchart with enabled "pan" option, if I hide all the children of one of the topmost parents then the chart disappear from screen. It seems that we need to add a reset button to keep the chart visible.
For details, please refer to the [issue](https://github.com/dabeng/OrgChart/issues/85) opened by [manuel-84](https://github.com/manuel-84) :blush:

Users can embed any clear up logics into the click handler of the reset buttton as shown below.
```js
$('.orgchart').css('transform',''); // remove the tansform settings
```

## Browser Compatibility
- Chrome 19+
- Firefox 4+
- Safari 6+
- Opera 15+
- IE 10+

## Charts Show
[I love NBA.](http://codepen.io/dabeng/full/aZzEVJ/)
![2016 NBA Playoff](http://dabeng.github.io/OrgChart/img/2016nba/2016-nba-playoff.png)

We thank [JordiCorbilla](https://github.com/JordiCorbilla):blush: for his sharing [how to save datasource after chart editing](https://github.com/dabeng/OrgChart/issues/34).
![save datasource](https://cloud.githubusercontent.com/assets/7347994/16707530/d7e206ca-45c9-11e6-9a93-5b29840de272.png)
