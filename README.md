# Trace to Scale

**Version 1.6 (20 October 2026)**

**[Open the tool](https://kcow3.github.io/trace-to-scale/)** · [Repository](https://github.com/kcow3/trace-to-scale)

Trace to Scale turns a photo of a real object into an accurate, to-scale sketch for your CAD app: Fusion 360, FreeCAD, Onshape, SolidWorks, KiCad, OpenSCAD and others. You photograph the part next to something of known size, calibrate the scale, trace the outline (by hand or automatically), adjust it for 3D-printing tolerances, and export it in millimetres.

It is a single HTML file. There is nothing to install and no internet connection is needed, apart from loading the fonts.

### What's new in 1.6

- **Export for other CAD apps.** Step 7 now has an **Export for** menu: Fusion 360, FreeCAD, Onshape, SolidWorks/Inventor/Solid Edge, KiCad, OpenSCAD, and laser cutters or Inkscape. Each choice gives the right file and import steps. FreeCAD gets a macro that builds an editable sketch, and OpenSCAD gets a ready-to-render plate. See [Bringing your work into your CAD app](#bringing-your-work-into-your-cad-app).

### What's new in 1.5

- **Symmetry tools for rotating.** An alignment grid with a centre line, a mirror check that overlays the outline flipped across that line, a live symmetry score, and **Straighten by symmetry**, which finds the most symmetrical angle for you. See [Getting a part symmetrical](#getting-a-part-symmetrical).

### What's new in 1.4

- **Rotate the photo with the drawing.** Rotating now turns the photo too, so your trace stays lined up and you can keep editing or trace more. If you rotated a drawing on its own, one click lines the photo up with it again.

### What's new in 1.3

- **Rotate shapes.** Straighten a traced part that sat slightly askew in the photo: drag a rotate handle, nudge by 1° or 0.1°, or click two points along a straight edge to level it. See [Rotating shapes](#rotating-shapes).

### What's new in 1.2

- **Language support.** The whole interface is available in English, Afrikaans and Czech. See [Language](#language).

### What's new in 1.1

- **Step-by-step wizard.** The left panel now shows one step at a time, with a progress strip, Back and Next buttons, and a note explaining what is needed to continue.
- **Seven steps instead of five.** Tracing, refining, print fit and export each have their own step, so no single screen is crowded.
- **Your shapes panel.** The shape list, Undo, Clear and the view options (units, grid) appear together in steps 4 to 6.

---

## Contents

1. [Getting started](#getting-started)
2. [Taking a good photo](#taking-a-good-photo)
3. [How the wizard works](#how-the-wizard-works)
4. [The workflow, step by step](#the-workflow-step-by-step)
5. [Auto trace](#auto-trace)
6. [Editing points](#editing-points)
7. [Smoothing](#smoothing)
   - [Rotating shapes](#rotating-shapes)
   - [Getting a part symmetrical](#getting-a-part-symmetrical)
8. [Print fit: scale and tolerances](#print-fit-scale-and-tolerances)
9. [Bringing your work into your CAD app](#bringing-your-work-into-your-cad-app)
10. [Mouse and keyboard reference](#mouse-and-keyboard-reference)
11. [Saving and reopening projects](#saving-and-reopening-projects)
12. [Language](#language)
13. [Troubleshooting](#troubleshooting)
14. [Roadmap](#roadmap)

---

## Getting started

1. Open the [live tool](https://kcow3.github.io/trace-to-scale/) in Chrome, Edge or Firefox. To use it offline, download `index.html` and open it in your browser.
2. Drag a photo onto the dark green area, paste one with **Ctrl+V**, or click **Choose photo**.
3. Pick your language at the top right if needed.
4. Follow the wizard in the left panel. See [How the wizard works](#how-the-wizard-works).

The **3D model** tab is a placeholder for a future version.

---

## Taking a good photo

The photo determines the accuracy more than anything else in the tool.

- **Shoot straight down** at the face you want to draw. If you can't, use step 2 to correct the perspective.
- **Stand back and zoom in.** Phone lenses distort near the edges of the frame when used close up. Keep the part in the middle of the shot.
- **Include a reference object** that lies flat, beside the part, at the same height as the face you're drawing. Good choices are a steel ruler, a bank card (85.60 × 53.98 mm), an A4 sheet, or a coin.
- **Use a plain, contrasting background**: white paper for dark parts, dark card for light or shiny parts.
- **Use soft, even light** from above. Hard side light casts shadows that get traced as part of the object.

---

## How the wizard works

The progress strip at the top of the left panel shows the seven steps:

| # | Step | Required? | Done when |
|---|---|---|---|
| 1 | **Photo** | Yes | A photo is loaded |
| 2 | **Angle** | Optional | The perspective is corrected or the photo is levelled |
| 3 | **Scale** | Yes | The reference line has a real length |
| 4 | **Trace** | Optional | At least one shape is traced or drawn |
| 5 | **Refine** | Optional | Shapes are edited or smoothed |
| 6 | **Fit** | Optional | Print scale or offsets are set |
| 7 | **Export** | | Download your files |

- **Next** is greyed out until the current step is complete. A short note explains what's missing.
- Optional steps show **Skip** until you use them. If you haven't traced anything, step 4 offers **Skip to export**, which is handy when you only want a calibrated photo to sketch over in your CAD app.
- **Back** returns to the previous step. Nothing is lost when you go back.
- Click any step in the strip to jump to it. Steps 2 and 3 unlock once a photo is loaded, and steps 4 to 7 once the scale is set.
- The wizard moves forward on its own when it makes sense:
  - Loading a photo goes to step 2.
  - Applying the perspective correction sets the scale and goes straight to step 4.
  - Pressing **Enter** in the length box in step 3 goes to step 4.
- Each step switches on the right tool: the reference line in step 3, **Auto trace** in step 4, **Edit points** in step 5.
- Keyboard shortcuts work from anywhere and jump to the matching step. For example, **E** opens step 5.

---

## The workflow, step by step

### Step 1: Load a photo

Drop, paste or choose an image (JPG, PNG or WebP). Very large photos are reduced to about 36 megapixels to keep the tool responsive. iPhone HEIC photos need converting to JPG first.

### Step 2: Angle (optional)

Use this when the photo was taken at an angle.

**Fix perspective.** This is the most accurate way to work.

1. Choose the reference rectangle (bank card, A4, A5, US Letter) or enter a custom size.
2. Click **Mark 4 corners**, then click the four corners of that rectangle in the photo, in any order.
3. Drag the corners to fine-tune them. The magnifier in the top corner helps with this.
4. Click **Apply correction**.

The photo is warped so that it looks as if it was taken straight on, and **the scale is set automatically** from the rectangle. Portrait and landscape orientation are detected for you.

**Level an edge.** Click two points along an edge that should be horizontal or vertical. The photo rotates to straighten it.

**Rotate 90°.** Turns the photo left or right.

> Anything you have already drawn moves with the photo when you straighten or rotate it, but undo history is cleared.

### Step 3: Set the scale

Skip this step if you used **Fix perspective**, because the scale is already set.

1. Click **Draw reference line** (or press **K**).
2. Click both ends of your known object.
3. Type its real length and choose mm, cm or inches, or pick a known object from the list (bank card, A4, South African R5/R2/R1 coins, US quarter, €1 coin, AA battery, 100 mm on a ruler).

The panel shows the scale in pixels per mm and the real size the whole photo covers. You can drag the ends of the yellow reference line at any time, and everything updates.

> **Accuracy tip:** use the longest known distance you can. If the reference line is under 250 pixels long, the tool warns you, because being one pixel off then matters a lot.

### Step 4: Trace

| Tool | Key | How to use it |
|---|---|---|
| Auto trace | A | Box around the part. See [Auto trace](#auto-trace). |
| Measure | M | Click two points to measure. Measurements don't go into the DXF unless you ask for them. |
| Line | L | Click start, click end. |
| Polyline | P | Click points one after another. Click the first point to close the shape, or press **Enter** or double-click to finish it open. |
| Rectangle | R | Click two opposite corners. |
| Circle | C | Click the centre, then any point on the edge. |
| Set origin | O | Click the point that should be **0,0** in your CAD app. By default the origin is the bottom-left corner of the photo. |
| Edit points | E | Select, move, add and delete points. See [Editing points](#editing-points). |

While drawing:

- New points **snap** to existing points within about 10 pixels. A white ring shows when a point will snap.
- Hold **Shift** to lock the angle to 15° steps.
- Live length and angle show in the status bar at the bottom.
- The **magnifier** in the top corner follows the cursor for precise clicks.
- Click-and-drag pans in any tool. A click without dragging places a point.

**Your shapes panel.** In steps 4 to 6, every shape and measurement appears in a list under the step. Hover over an item to highlight it on the photo, click a shape to select it for editing (this opens step 5), or click **×** to delete it. **Undo** and **Clear drawing** sit underneath. **View options** holds **Show in** (mm, cm or inches) and **Grid every … mm**, which overlays a grid in real units measured from your origin.

### Step 5: Refine (optional)

Tidy up the traced shapes with **Edit points**, the **Smoothing** slider and **Rotate**. See [Editing points](#editing-points), [Smoothing](#smoothing) and [Rotating shapes](#rotating-shapes).

### Step 6: Fit (optional)

Adjust the exported shapes for printer tolerances. See [Print fit](#print-fit-scale-and-tolerances).

### Step 7: Export

Choose an export, or save the project. Details are in [Bringing your work into your CAD app](#bringing-your-work-into-your-cad-app). **Start with a new photo** loads another image.

---

## Auto trace

Auto trace finds the outline of a part, and any holes in it, for you.

1. Set the scale first, so results come out in mm.
2. Choose **Auto trace outline** (or press **A**).
3. Click two corners of a box around the part. **Leave some background showing on every side**, because the tool works out the background colour from the edge of the box. You can also click **trace the whole photo**.
4. Check the preview. Outer outlines show in orange and holes in yellow. Round holes are converted to true circles with their diameter shown.
5. Adjust the settings if needed, then click **Add to drawing** (or press **Enter**).

| Setting | What it does |
|---|---|
| **Sensitivity** | Raise it if parts of the outline are missing. Lower it if background is being picked up. |
| **Simplify** | How far the outline may stray from the true edge before another point is added. Higher values give fewer, straighter segments. |
| **Ignore specks** | Drops dust, scratches and texture smaller than the size shown. |
| **Include holes and cut-outs** | Also traces openings inside the part. |
| **Turn round shapes into circles** | Converts near-perfect circles into exact circles, which are much nicer to work with in CAD. |
| **Reduce shadows** | Compares colour more than brightness, so grey shadows are less likely to be traced. |

Auto trace compares each pixel's colour to the background rather than just looking for dark areas, so dark, light and coloured parts all work. It finds edges with sub-pixel precision.

---

## Editing points

Edit points is in **step 5 (Refine)**. Press **E** to jump there from any step.

| Action | How |
|---|---|
| Select a shape | Click its outline, or click it in the shape list |
| Move a point | Drag it |
| Select several points | Drag a box across empty space around them |
| Add or remove points from the selection | Shift-click, or Ctrl-click |
| Move several points | Select them, then drag any one of them |
| Move the whole shape | Drag the outline between points |
| Add a point | Double-click on a line |
| Delete points | Select them and press **Delete**, or click **Delete points**. The outline joins straight across the gap. |
| Soften a bumpy section | Select the points and click **Smooth selected points**. Click again for more. |
| Delete the shape | Select it and click **Delete shape**, or press **Delete** with no points selected |
| Clear the selection | **Esc**, or click on empty space |
| Pan while editing | Right-drag, middle-drag, or hold **Space** and drag |

> **Fixing notches and glitches:** box-select the points around the problem and press **Delete**. The outline bridges straight across. For a curved section, use **Smooth selected points** instead.

---

## Smoothing

The **Smoothing** slider is in **step 5 (Refine)** and appears once you have outlines or polylines. It removes small bumps and jaggies from the outline without shrinking the shape.

- With **no shape selected**, it applies to all outlines. With a shape selected in Edit points, it applies to that shape only.
- The value shown is roughly how large a bump it irons out, in mm.
- Higher values also round off sharp corners. Turn it down if corners need to stay crisp.
- Smoothing doesn't permanently change the outline: setting the slider back to **0 (Off)** restores the original trace.
- If you edit points by hand after smoothing, the current smoothed shape becomes the new starting point and the slider resets to 0 for that shape.

### Rotating shapes

Parts don't always sit perfectly square to the ruler. The **Rotate** section in step 5 turns your traced shapes so they come into your CAD app straight.

| Method | How |
|---|---|
| **Drag the handle** | Drag the round yellow handle above the shapes. The angle shows as you drag, in 0.1° steps. Hold **Shift** for 15° steps. |
| **Nudge** | Click **⟲ 1°**, **⟲ 0.1°**, **0.1° ⟳** or **1° ⟳**. |
| **Level by two points** | Click the button, then click both ends of a straight edge on the part (a USB slot or a flat side works well). The shapes rotate so that edge is exactly horizontal or vertical. |

**Rotate the photo too** (on by default) decides what turns:

- **On:** the photo and everything on it rotate together: shapes, measurements, the reference line and the origin. The trace stays exactly on the part, so you can go back and edit points, smooth, or trace more. The photo is always redrawn from the original, so repeated small turns don't blur it.
- **Off:** only the drawing rotates and the photo stays put. All shapes rotate together around their shared centre, so holes stay in place on the outline. To rotate **one shape only**, select it with Edit points first.

If you rotated the drawing on its own and later want to edit over the photo again, click **Line up the photo with the drawing**. The photo turns to match, and everything lines up as if you had rotated them together. The button appears only while that's possible; drawing a new shape afterwards ends the option, because the new shape was drawn on the unrotated photo.

- Rectangles become 4-point outlines once rotated, so they can sit at an angle.
- Undo (**Ctrl+Z**) reverses any rotation, including the photo's.
- Rotation never changes sizes, so the scale stays correct.

### Getting a part symmetrical

Most parts are symmetrical, so symmetry is the best guide for getting them straight. These tools sit under the rotate buttons in step 5:

| Tool | What it does |
|---|---|
| **Alignment grid** | A square grid over the canvas, with a dashed **yellow centre line** through the middle of the main outline. The grid stays fixed while the part turns underneath it. It also appears whenever you drag the rotate handle. |
| **Mirror check** | Draws a **dashed pink copy** of every shape, flipped across the centre line. Choose **Left ↔ right** for parts that are symmetrical side to side, or **Top ↔ bottom** for parts that are symmetrical top to bottom. When the part is straight, the pink copy sits right on top of the outline. |
| **Symmetry difference** | The average gap, in mm, between the outline and its mirror image. Lower is more symmetrical. While you drag the rotate handle it shows next to the angle, so you can turn until it's as low as it goes. |
| **Straighten by symmetry** | Searches angles up to ±20° and rotates to the one with the lowest symmetry difference, to the nearest 0.02°. The message shows the angle and how much the difference dropped, for example *0.91 mm → 0.06 mm*. |

- The score uses the largest closed outline. Holes are mirrored in the overlay so you can check they're centred, but they don't count towards the score.
- A real part is never perfectly symmetrical, so the difference won't reach zero. A few hundredths of a millimetre is excellent.
- It follows the **Rotate the photo too** setting, so the photo turns with the drawing when that's on.

> **Step 2 or step 5?** Both can straighten the photo. **Level an edge** in step 2 is handy before you start tracing. The Rotate tools in step 5 work at any point and keep your drawing in place.

---

## Print fit: scale and tolerances

These settings are in **step 6 (Fit)** and change **the exported shapes only**. The trace on the photo stays as it is.

| Setting | Steps | Use it for |
|---|---|---|
| **Scale %** | 0.1% | Scales the whole drawing, for example 100.2% to make up for material shrinkage. |
| **Outlines ± mm** | 0.05 mm | Grows (positive) or shrinks (negative) the outer outlines by an exact distance on every edge. |
| **Holes ± mm** | 0.05 mm | Same, for any shape that sits inside another outline. Positive makes the hole bigger. |

When any of these is active:

- A **white dashed line** shows the print shape over the photo (turn it off with **Show the print shape on the photo**).
- The shape list shows **Print:** sizes next to the traced sizes.
- The panel shows the overall print size next to the traced size.
- **DXF, SVG and CSV exports use the adjusted shape.**

### Choosing a value

- **A case, pocket or holder the part must fit into:** grow **Outlines** by your printer's clearance, typically **+0.2 to +0.4 mm** for FDM.
- **A replacement part that must fit into an existing opening:** shrink **Outlines**, typically **−0.1 to −0.2 mm**.
- **Screw or pin holes that print too tight:** grow **Holes**, typically **+0.2 to +0.3 mm**.

> **Offset or scale?** For tolerances, an mm offset is usually better than scaling. A 1% scale adds 0.5 mm per side on a 100 mm part but only 0.1 mm on a 20 mm part, while an offset gives the same clearance on every edge. Use scale only for overall shrinkage correction.

A quick way to dial in your printer: print a thin test plate of the outline, check the fit, adjust the offset, and print again.

---

## Bringing your work into your CAD app

### Choose your app

Pick your app under **Export for** at the top of step 7. You get the right file and short import steps for it, and the tool remembers your choice. Every export is in millimetres, positioned relative to your origin, and includes your [Print fit](#print-fit-scale-and-tolerances) settings.

| App | File | How to bring it in |
|---|---|---|
| **Fusion 360** | DXF | **Insert › Insert DXF**, pick a plane, units mm. |
| **FreeCAD** | Sketch macro (`.FCMacro`), or DXF | Open the macro with **File › Open**, then **Macro › Execute macro**. It builds an editable **Sketcher** sketch with joined, closed outlines that are ready to **Pad**. Or import the DXF with **File › Import**. |
| **Onshape** | DXF | Import the DXF into your document. In a sketch, click **Insert DXF or DWG** and set the units to millimetre. |
| **SolidWorks, Inventor, Solid Edge** | DXF | **File › Open** the DXF and import it as a 2D sketch in a new part, units millimetres. |
| **KiCad** | DXF | PCB Editor: **File › Import › Graphics**, layer **Edge.Cuts**, units mm. Holes become cut-outs in the board. |
| **OpenSCAD** | `.scad` | Open it, set `thickness` at the top (or choose it before downloading), press **F6** and export STL. Outlines become a solid plate and holes are cut through. Open lines are left out. |
| **Laser cutter or Inkscape** | SVG | Open in Inkscape, LightBurn or your laser software. True size in mm, with 0.3 mm lines. |

Using a different app? Download the **DXF**. It's the most widely supported format and works in almost any CAD program; just make sure the import units are set to millimetres.

### About the DXF

- Traced geometry is on the `TRACE` layer. Tick **Include measure lines on their own layer** to also bring in your measurements on a separate `MEASURE` layer.
- Outlines come in as connected line segments and holes as true circles where the tool recognised them.
- Use it directly, or as an accurate guide for a cleaner sketch with proper constraints.

### Sketching over the photo instead

If you'd rather draw over the photo in your CAD app:

1. Click **Download scaled photo (PNG)**. Keep **Add a scale bar** ticked, and optionally tick **Include traced lines**.
2. Place the image in your CAD app and scale it using the scale bar, whose length is printed next to it:
   - **Fusion 360:** **Insert › Canvas**, then right-click the canvas › **Calibrate**, click both ends of the scale bar and type its length.
   - **FreeCAD:** in the **Image** workbench, create an image plane, then use **Scale image**: click both ends of the scale bar and enter its length.
   - **Other apps:** most can place an image in a sketch (in SolidWorks it's called **Sketch Picture**). Resize it until the scale bar matches its printed length.
3. Sketch over the photo.

The file name includes the scale in pixels per mm, for reference.

### Other exports

- **SVG:** the drawing as a true-size vector file (units in mm). It can optionally include the photo, which is useful for laser cutters, Inkscape and documentation.
- **Measurements (CSV):** every measurement and shape dimension, plus the print-fit settings, for a spreadsheet.

---

## Mouse and keyboard reference

| Input | Action |
|---|---|
| Scroll wheel | Zoom at the cursor |
| Drag (any tool) | Pan |
| Right-drag, middle-drag, Space + drag | Pan (also works in Edit points) |
| Pinch (touch) | Zoom |
| Drag a point | Move it |
| Shift (while drawing) | Lock the angle to 15° steps |
| Enter | Finish a polyline, or add the auto-trace result |
| Esc | Cancel the current shape, discard the auto-trace preview, or clear the selection |
| Backspace | Remove the last point while drawing |
| Delete | Delete selected points or shape (Edit points) |
| Ctrl+Z / Ctrl+Y | Undo / redo (Ctrl+Shift+Z also redoes) |
| V K M L P R C A E O | Pan, reference line, measure, line, polyline, rectangle, circle, auto trace, edit points, origin |
| F | Fit the photo to the view |
| G | Toggle the grid |
| + / − | Zoom in / out |

---

## Saving and reopening projects

- **Save project** (step 7) downloads a `.trace.json` file containing the photo and everything you've done: corrections, scale, shapes, smoothing, origin and print-fit settings.
- **Open project** (step 1) loads it again so you can continue. You can also drag a `.trace.json` file onto the canvas.

---

## Language

Choose **English**, **Afrikaans** or **Čeština** (Czech) from the language menu at the top right. The change is instant and covers everything on screen: the wizard, buttons, hints, messages and labels drawn on the photo. Your work is not affected.

- The tool remembers your choice for next time. On first use it follows your browser language.
- CAD menu names in the export tips (such as **Insert › Insert DXF** or **Macro › Execute macro**) stay in English, because that is how they appear in the English versions of those apps.
- Exported files (DXF, SVG, CSV, project files) are the same in every language. CSV column names stay in English so spreadsheets stay consistent.
- Decimal numbers always use a full stop (for example 0.25 mm), in every language.

---

## Files in this repository

| File | What it is |
|---|---|
| `index.html` | The tool (latest version). GitHub Pages serves this as the home page. |
| `README.md` | This guide. |
| `versions/` | Earlier versions, kept for reference: `v1.0.html` (first release), `v1.1.html` (wizard), `v1.2.html` (languages), `v1.3.html` (rotate shapes), `v1.4.html` (rotate the photo with the drawing), `v1.5.html` (symmetry tools), `v1.6.html` (export for other CAD apps, same as `index.html`). |

---

## Troubleshooting

| Problem | Try this |
|---|---|
| "This browser can't open that image" | Convert HEIC or RAW photos to JPG first. |
| Measurements are slightly off | Use a longer reference, shoot from further away with zoom, or use Fix perspective with a bank card or A4 sheet. Check by measuring a second known feature. |
| Next is greyed out | Read the note above the button. Steps 1 and 3 must be completed before moving on. |
| Steps 4 to 7 are locked in the strip | Set the scale in step 3 first. |
| Auto trace finds nothing | Raise **Sensitivity**, and make sure the box has background showing on all four sides. |
| Auto trace includes the shadow | Tick **Reduce shadows**, lower **Sensitivity**, or reshoot with softer light. |
| Auto trace outline is bumpy | Raise **Simplify**, or use the **Smoothing** slider after adding. |
| Small glitches or notches in the outline | Use **Edit points**: box-select the bad points and press **Delete**. |
| Can't pan while editing points | Right-drag, middle-drag, or hold **Space** and drag. |
| Holes aren't treated as holes in Print fit | A shape counts as a hole only when it sits inside another closed outline. |
| Fonts look different | The fonts load from the internet. Offline, the tool falls back to your system font and works the same. |

---

## Roadmap

Ideas for future versions:

- **3D import:** open STL, OBJ and 3MF files, measure them, and slice them into section profiles for CAD sketches.
- **Corner and line cleanup:** snap nearly-straight runs to exact lines and nearly-square corners to 90°.
- **Arc fitting:** export curved sections as true arcs instead of short line segments.
- **Splines:** draw smooth curves through clicked points, exported as editable splines.
- **Lens distortion correction:** for wide-angle phone photos.
- **Two-view mode:** a top and a side photo at the same scale, for profile and depth.
- **Accuracy check:** measure a second known feature and see the percentage error.

---

*Trace to Scale v1.6. A single-file HTML tool for creating to-scale CAD sketches from photos.*
