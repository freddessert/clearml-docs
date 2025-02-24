---
title: Working with Frames
---

View and edit SingleFrames in the Dataset page. After selecting a Hyper-Dataset version, the **Version Browser** shows a sample 
of frames and enables viewing SingleFrames and FramesGroups, and edit SingleFrames, in the [frame viewer](#frame-viewer). 
Before opening the frame viewer, you can filter the frames by applying [simple](#simple-frame-filtering) or [advanced](#advanced-frame-filtering) 
filtering logic. 

![Dataset page](../../img/hyperdatasets/web-app/dataset_simple_adv_02.png)

## Frame Viewer

Frame viewer allows you to view and edit annotations which can be FrameGroup objects (Regions of Interest) and FrameGroup 
labels applied to the entire frame not a region of the frame, the frame details (see [frames](../frames.md)), 
frame metadata, the raw data source URI, as well as providing navigation and viewing tools. 

![Frame viewer](../../img/hyperdatasets/web-app/dataset_example_frame_editor.png)

### Frame Viewer Controls

Use frame viewer controls to navigate between frames in a Hyper-Dataset Version, and control frame changes and viewing.

|Control Icon|Actions|Shortcut|
|-----|------|----|
|<img src="/docs/latest/icons/ico-skip-backward.svg" alt="Jump backwards icon" className="icon size-md space-sm" />| Jumps backwards ten frames | CTRL + Left arrow |
|<img src="/docs/latest/icons/ico-skip-previous.svg" alt="Jump to previous unfiltered annotation" className="icon size-md space-sm" />|Go to the previous frame containing a non-filtered annotation. The filter is the minimum confidence level setting. If the confidence level filter is set to zero, any frame containing annotations matches the filter.| <img src="/docs/latest/icons/ico-optional-no.svg" alt="Not applicable" className="icon size-md center-md" /> |
|<img src="/docs/latest/icons/ico-arrow-left.svg" alt="Previous frame icon" className="icon size-md space-sm" />|Go to the previous frame | Left arrow |
|<img src="/docs/latest/icons/ico-arrow-right.svg" alt="Next frame icon" className="icon size-md space-sm" />|Go to the next frame | Right arrow |
|<img src="/docs/latest/icons/ico-skip-next.svg" alt="Jump to next unfiltered annotation" className="icon size-md space-sm" />|Go to the next frame containing a non-filtered annotation (same filter as <img src="/docs/latest/icons/ico-skip-previous.svg" alt="Jump to previous unfiltered annotation" className="icon size-md space-sm" />).| <img src="/docs/latest/icons/ico-optional-no.svg" alt="Not applicable" className="icon size-md center-md" /> |
|<img src="/docs/latest/icons/ico-skip-forward.svg" alt="Jump forwards icon" className="icon size-md space-sm" />|Jump forwards ten frames | CTRL + Right arrow |
|<img src="/docs/latest/icons/ico-revert.svg" alt="Reload frame icon" className="icon size-md space-sm" />|Reload the frame.| <img src="/docs/latest/icons/ico-optional-no.svg" alt="Not applicable" className="icon size-md center-md" /> |
|<img src="/docs/latest/icons/ico-undo.svg" alt="Undo icon" className="icon size-md space-sm" />|Undo changes.|Ctrl + Z| 
|<img src="/docs/latest/icons/ico-redo.svg" alt="Redo icon" className="icon size-md space-sm" />|Redo changes.|Ctrl + Y| 
|<img src="/docs/latest/icons/ico-reset_1.svg" alt="Autofit icon" className="icon size-md space-sm" />|Autofit| <img src="/docs/latest/icons/ico-optional-no.svg" alt="Not applicable" className="icon size-md center-md" /> |
|<img src="/docs/latest/icons/ico-zoom-in.svg" alt="Zoom in icon" className="icon size-md space-sm" />|Zoom in| **+** or Ctrl + Mouse wheel| 
|<img src="/docs/latest/icons/ico-zoom-out.svg" alt="Zoom out icon" className="icon size-md space-sm" />|Zoom out| **-** or Ctrl + Mouse wheel |
|Percentage textbox|Zoom percentage| <img src="/docs/latest/icons/ico-optional-no.svg" alt="Not applicable" className="icon size-md center-md" /> |


#### Additional Keyboard Shortcuts

**General Controls**

|Control|Action|
|----|-----|
|Hold Spacebar + Press and hold image + Drag| Move around image. NOTE: If using a touchpad, this only works if the *Disable touchpad while typing* setting is turned off | 
|Esc | Escape frame viewer and return to dataset page |

**General Annotation Controls**

|Control|Action|
|----|-----|
| Delete | Remove annotation |
| Alt + ] / [ | Choose a default ROI label by navigating between previous / next labels  |
| Shift + M | Edit metadata | 
| Shift + Tab | Previous annotation (use after clicking an annotation) |

**Mode-specific annotation controls**

|Control |Mode |Action|
|----|-----|----|
| Hold Shift | Key points (<img src="/docs/latest/icons/ico-keypoint-icon-purple.svg" alt="Key points mode" className="icon size-sm space-sm" />) | While holding Shift, add new points to the ROI by left clicking, and move a single point by dragging it with your mouse | 
| Enter | Key points (<img src="/docs/latest/icons/ico-keypoint-icon-purple.svg" alt="Key points mode" className="icon size-sm space-sm" />) | Complete annotation |
| Esc | Key points (<img src="/docs/latest/icons/ico-keypoint-icon-purple.svg" alt="Key points mode" className="icon size-sm space-sm" />), Polygon (<img src="/docs/latest/icons/ico-polygon-icon-purple.svg" alt="Polygon mode" className="icon size-sm space-sm" />) | Cancel annotation process | 

### Viewing and Editing Frames

**To view / edit a frame in the frame editor**

1. Locate your frame by applying a [simple frame filter](#simple-frame-filtering) or [advanced frame filter](#advanced-frame-filtering), and clicking **LOAD MORE**, if required.
1. Click the frame thumbnail. The frame editor appears.
1. Do any of the following:
    * View frame details, including:
        * Frame file path
        * Dimensions of the image or video
        * Frame details
        * Frame metadata
        * Annotations
            * Frame objects - Labeled Regions of Interest, with confidence levels and custom metadata per frame object.
            * Frame labels - Labels applied to the entire frame, not a region in the frame.
    * Optionally, filter annotations by confidence level using the **Minimum confidence** slider.
    * Add, change, and delete [annotations](#annotations) and [frame metadata](#frame-metadata).
      
:::important Saving Frame Changes
To save frames changes at any time, click **SAVE** (below the annotation list area).
:::
 

### Viewing FrameGroups

Viewing and editing frames in a FrameGroup is similar to viewing and editing SingleFrames. 
Click the FrameGroup in the Hyper-Dataset. In the frame viewer, select SingleFrame to view / modify from 
a dropdown list in the **Current Source** section.

![Frame dropdown menu in FrameGroup](../../img/hyperdatasets/framegroup_01.png)

## Filtering Frames
### Simple Frame Filtering

Simple frame filtering applies one annotation object (ROI) label and returns frames containing at least one annotation 
with that label. 

**To apply a simple frame filter:**

* In the **Version Browser**, choose a label on the label list.

For example: 
* The **version browser** in the image below contains 101 frames.

<details className="cml-expansion-panel screenshot">
<summary className="cml-expansion-panel-summary">View a screenshot</summary>
<div className="cml-expansion-panel-content">
      

![Unfiltered version browser](../../img/hyperdatasets/frame_filtering_01.png)


</div>      
</details>
<br/>  

* A simple label filter for `teddy bear` shows three frames with each containing at least one ROI labeled `teddy bear`.

<details className="cml-expansion-panel screenshot">
<summary className="cml-expansion-panel-summary">View a screenshot</summary>
<div className="cml-expansion-panel-content">

![Filtered version browser](../../img/hyperdatasets/frame_filtering_02.png)

</div>
</details>

### Advanced Frame Filtering

Advanced frame filtering applies sophisticated filtering logic, which is composed of as many frame filters as needed, 
where each frame filter can be a combination of ROI, frame, and source rules. 
* ROI rules use include and exclude logic to match frames by ROI label; an ROI label can match frames containing at least 
  one annotation object (ROI) with all labels in the rule.
* Frame rules and source rules use Lucene queries with AND, OR, and NOT logic. Frame rules apply to frame metadata.
* Source rules apply to frame source information.

**To apply advanced filters:**

1. In the **Version Browser**, click **Switch to advanced filters**.
1. In a **FRAME FILTER**, create one of the following rules:

    * ROI rule

        * Choose **Include** or **Exclude**, select ROI labels, and optionally set the confidence level range.

        * To switch from the ROI dropdown list to a Lucene query mode, click <img src="/docs/latest/icons/ico-edit.svg" alt="edit pencil" className="icon size-md space-sm" />.
            
    * Frame rule - Enter a Lucene query using frame metadata fields in the format `meta.<key>:<value>`.
    
    * Source rule - Enter a Lucene query using frame metadata fields in the format `sources.<key>:<value>`.            

### Examples
        
#### ROI Rules


* Create one ROI rule for the `teddy bear` label, which shows the same three frames as the simple frame filter (above).
  <details className="cml-expansion-panel screenshot">
  <summary className="cml-expansion-panel-summary">View a screenshot</summary>
  <div className="cml-expansion-panel-content">

  ![Adding an ROI rule](../../img/hyperdatasets/frame_filtering_03.png)

  </div>
  </details>            
  <br/>

* In the ROI rule, add a second label. Add `partially_occluded`. Only frames containing at least one ROI labeled as both 
  `teddy bear` and `partially_occluded` match the filter.
<details className="cml-expansion-panel screenshot">
   <summary className="cml-expansion-panel-summary">View a screenshot</summary>
   <div className="cml-expansion-panel-content">

   ![Add label to ROI rule](../../img/hyperdatasets/frame_filtering_04.png)

   </div>
   </details>            
   <br/>

   By opening a frame in the frame viewer, you can see an ROI labeled with both.

   <details className="cml-expansion-panel screenshot">
   <summary className="cml-expansion-panel-summary">View a screenshot</summary>
   <div className="cml-expansion-panel-content">

   ![Labeled ROIs in frame viewer](../../img/hyperdatasets/frame_filtering_05.png)

   </div>
   </details>            
   <br/>


#### Frame Rules

Filter by metadata using Lucene queries.

* Add a frame rule to filter by the metadata key `dangerous` for the value of `yes`.

    <details className="cml-expansion-panel screenshot">
    <summary className="cml-expansion-panel-summary">View a screenshot</summary>
    <div className="cml-expansion-panel-content">

    ![Filter by metadata ](../../img/hyperdatasets/frame_filtering_08.png)

    </div>
    </details>            
    <br/>

    By opening a frame in the frame viewer, you can see the metadata.

    <details className="cml-expansion-panel screenshot">
    <summary className="cml-expansion-panel-summary">View a screenshot</summary>
    <div className="cml-expansion-panel-content">

    ![Frame metadata in frame viewer](../../img/hyperdatasets/frame_filtering_09.png)

    </div>
    </details>            
    <br/>

    
#### Source Rules

Filter by sources using Lucene queries.    

* Add a source rule to filter for sources URIs with wildcards.

    <details className="cml-expansion-panel screenshot">
    <summary className="cml-expansion-panel-summary">View a screenshot</summary>
    <div className="cml-expansion-panel-content">

    ![Filter by source](../../img/hyperdatasets/frame_filtering_10.png)

    </div>
    </details>            
    <br/>

Lucene queries can also be used in ROI label filters and frame rules.        

## Masks 

Use the **MASKS** panel to select which masks to apply over the frame. 

To view / hide a specific mask, click <img src="/docs/latest/icons/ico-show.svg" alt="Eye Show" className="icon size-md space-sm" />.
In order to view all masks, click **Show all** / **Hide all**. 

Masks are applied over the image either by pixel segmentation or as an alpha channel:
* <img src="/docs/latest/icons/ico-segmentation.svg" alt="Pixel segmentation mode" className="icon size-md space-sm" /> Pixel 
segmentation - Class labels are mapped onto the mask according to their pixel value definitions, and each 
class is assigned a unique color. 
* <img src="/docs/latest/icons/ico-alpha-mask.svg" alt="Alpha channel mode" className="icon size-md space-sm" /> Alpha 
channel - Mask pixel values are translated to transparency. Additionally, a color can be applied to the mask to help 
distinguish multiple masks. Click <img src="/docs/latest/icons/ico-mask-color-preview.svg" alt="Alpha color" className="icon size-md space-sm" /> to select 
a color. 

To adjust the transparency of a mask, use its opacity slider. 

### Labels 

The **Active mask labels** section displays the color mapping of the mask labels. 
The panel presents labels only from masks that are currently displayed.

**To modify a label's color and opacity:**
1. Click the colored circle next to the label 
1. Select a new color
1. Adjust the opacity slider 
1. Click **OK**

## Annotations
### Adding Frame Objects (Regions of Interest)

You can add annotations by drawing new bounding areas, and copying existing annotations in the same or other frames.

#### Creating New Frame Objects

To draw a bounding area for a new annotation:

1. Click one of the following modes and create a bounding area in the frame:   
   
    * <img src="/docs/latest/icons/ico-rectangle-icon-purple.svg" alt="Rectangle mode icon" className="icon size-md space-sm" /> - Rectangle mode: Drag a 
   rectangle onto the frame.   
    
    * <img src="/docs/latest/icons/ico-ellipse-icon-purple.svg" alt="Ellipse mode icon" className="icon size-md space-sm" /> - Ellipse mode: Drag an ellipse 
   onto the frame.   
    
    * <img src="/docs/latest/icons/ico-polygon-icon-purple.svg" alt="Polygon mode icon" className="icon size-md space-sm" /> - Polygon mode: Click the polygon
   vertices onto the frame.       
    
    * <img src="/docs/latest/icons/ico-keypoint-icon-purple.svg" alt="Key points mode icon" className="icon size-md space-sm" /> - Key points mode: Click each 
   keypoint onto the frame. After the clicking the last keypoint, click the first again to close the bounding area.   

    A new annotation is created. 

1. In the newly created annotation, select or type-in a label(s). Click the circle in the label name to select a 
   different label color. 

You can use the **Default ROI Label(s)** list to automatically set labels to all new annotations. 

#### Copying Frame Objects 
You can copy existing annotations, and paste them to any frame of your choice:
1. Click the annotation or bounded area in the frame.
1. Click <img src="/docs/latest/icons/ico-copy-to-clipboard.svg" alt="Copy annotation" className="icon size-md space-sm" /> 
   (copy annotation).
1. Navigate to the frame of your choice (you can remain in the same frame).
1. Click **PASTE**. The new annotation appears in the same location as the one you copied. You can paste the annotation
   multiple times.
   
Copy all annotations in a frame by clicking the **COPY ALL** button.

### Annotation Actions

The following table describes the actions that can be performed on existing annotations. The frame editor automatically 
saves changes when you move to another frame using the frame navigation controls 
(<img src="/docs/latest/icons/ico-arrow-right.svg" alt="Next frame icon" className="icon size-md space-sm" />, <img src="/docs/latest/icons/ico-skip-next.svg" alt="Jump to next unfiltered annotation" className="icon size-md space-sm" />, <img src="/docs/latest/icons/ico-skip-forward.svg" alt="Jump forwards icon" className="icon size-md space-sm" />, <img src="/docs/latest/icons/ico-arrow-left.svg" alt="Previous frame icon" className="icon size-md space-sm" />, <img src="/docs/latest/icons/ico-skip-previous.svg" alt="Jump to previous unfiltered annotation" className="icon size-md space-sm" />, <img src="/docs/latest/icons/ico-skip-backward.svg" alt="Jump backwards icon" className="icon size-md space-sm" />,
or the arrow keys on the keyboard). Closing the frame editor will prompt you to save any changes.

| Icon (when applicable) | Action | Description |
|---|---|---|
|| Move annotation | Click on a bounded area and drag it. |
|| Resize annotation| Select an annotation, then click on a bounded area’s vertex and drag it. |	
|<img src="/docs/latest/icons/ico-metadata.svg" alt="edit metadata" className="icon size-md space-sm" />|Edit metadata|Hover over an annotation in the list and click the icon to open the edit window. Input the metadata dictionary in JSON format. This metadata is specific to the selected annotation, not the entire frame.|
|<img src="/docs/latest/icons/ico-lock-open.svg" alt="Lock annotation" className="icon size-md space-sm" />|Lock / Unlock annotation |Click the button on a specific annotation to make it uneditable. You can also click the button on top of the annotations list to lock all annotations in the frame.|
|<img src="/docs/latest/icons/ico-trash.svg" alt="Trash" className="icon size-sm space-sm" />|Delete annotation|Click the annotation or bounded area in the frame and then click the button to delete the annotation.|
|<img src="/docs/latest/icons/ico-show.svg" alt="Eye Show All" className="icon size-md space-sm" />|Show/hide all annotations |Click the button to view the frame without annotations. When annotations are hidden, they can’t be modified. |
||Delete label |In the relevant annotation, click **x** on the label you want to remove.| 

### Frame Labels

You can add labels which describe the whole frame, with no specific coordinates. 

**To add frame labels:**

1. Expand the **FRAME LABELS** area (below **OBJECTS**)
1. Click **+ Add new**
1. Enter a label(s)

## Frame Metadata

**To edit frame metadata:** 
1. Expand the **FRAME METADATA** area 
1. Click edit <img src="/docs/latest/icons/ico-metadata.svg" alt="edit metadata" className="icon size-md space-sm" /> 
   which will open an editing window
1. Modify the metadata dictionary in JSON format


