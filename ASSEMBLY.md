# Assembly in Pictures

Deutsch: [ANLEITUNG.md](ANLEITUNG.md)

![Assembly animation](media/montage.gif)

As a video: [montage.mp4](media/montage.mp4).

Everything snaps or plugs together: no glue, no screws, no soldering. You need the printed
parts, the board and the battery, plus side cutters or pliers for the supports and a paper clip
for BOOT and RESET.

## Step 1: Print

| Plate | File | Profile (Bambu Studio, P1S) | Supports |
|---|---|---|---|
| 1 | `stl/front_multicolor.stl` (AMS) or `stl/front_single_color.stl` | `Digivice Front 0.16mm` + a PLA system profile | Normal supports, on build plate only, threshold angle 30° |
| 2 | `stl/back_clip_slider.stl` | `Digivice Back 0.16mm` + `Digivice PLA Back` | None (clip: optional, see below) |

| Plate 1 | Plate 2 |
|---|---|
| ![Plate 1: front](images/plate1.png) | ![Plate 2: back cover, clip, slider](images/plate2.png) |

Material: PLA for all parts, 0.16 mm layer height. The profiles are in `bambu-p1s/`; the
[README](README.md#profiles-for-bambu-studio-p1s) explains how to import them and lists their
settings. Print plate 2 with the filament profile `Digivice PLA Back`: it runs hotter and with
less cooling, so the layers of the snap hooks fuse well. No tree supports for the front: they
grow into the snap windows. The slider looks good in the button color.

On plate 2, Bambu Studio warns about “floating regions”. They are on the clip: its arm starts
6 mm above the plate, and its pegs stick out sideways. The back cover and the slider need no
supports. The README shows how to give the clip supports of its own and an optional brim.

**Multicolor with AMS:** load `front_multicolor.stl`, right-click it and choose **Split > To
parts**. You get five parts: body, three buttons, antenna. Assign a filament to each part. If
you give the antenna the body color, you save many color changes.

## Step 2: Remove the Supports

![Front after printing](images/steps/02_supports.png)

Remove the supports under the antenna, in the chamber under the front plate and in the pry
notch at the bottom edge. The chamber must be smooth, because the display glass rests against
it later. The eight snap windows in the wall must be clear, or the hooks will not engage. The
antenna is printed onto the front and stays attached.

## Step 3: Insert the Battery

![Battery in the back cover](images/steps/03_battery.png)

Place the battery in the frame in the back cover and run the cable with the connector through
the gap at the top of the frame. Later, the board holds the battery in place.

## Step 4: Attach the Clip (Optional)

| Clip from below | Above the holes | Attached |
|---|---|---|
| ![Clip from below](images/steps/04_clip_from_below.png) | ![Clip above the holes](images/steps/04_clip_over_holes.png) | ![Clip attached](images/steps/04_clip_attached.png) |

1. Hold the clip so that the bend points to the top edge of the back cover and the arm hangs
   down over the back.
2. Place the two pegs on the two holes above the cross grooves.
3. Press the base plate down with your thumb until it sits flat. The crush ribs on the pegs
   hold the clip.

To remove it, pull it straight off.

## Step 5: Insert the Board

![Board in the front](images/steps/05_board.png)

Plug the battery connector into the `BAT` socket; plus goes to the side marked +. Place the
board into the front from behind, display glass first: USB-C sockets into the bays at the
bottom, TF slot to the top left, BOOT and RESET buttons to the pinholes on the right.

## Step 6: Insert the Slider

![Slider](images/steps/06_slider.png)

The slider is the on/off switch. It moves the board’s own switch, whose lever sits deep in the
case under the board.

1. From outside, push the slider, fork first, through the slot in the right flank. The rib
   faces outward; the cross groove on the underside faces the back cover.
2. While pushing, move the slider up and down slightly until the fork straddles the lever and
   the grip sits in the recess.
3. Check: you can feel the slider click into two positions. Up is ON, down is OFF.

![Grip recess](images/steps/06_slider_recess.png)

## Step 7: Put On the Back Cover

![Putting on the back cover](images/steps/07_lid.png)

Place the back cover, with battery and clip, onto the front so that the outlines line up
exactly: then the eight hooks meet their windows. The four flat pillars in the back cover stand
just behind the board’s standoffs and hold the board in the chamber. The tab at the right edge
of the back cover slides through the slot in the wall into the cross groove of the slider and
holds the slider in place. For this, the slider must be pushed fully into its channel.

## Step 8: Snap It Shut

![Snapped shut](images/steps/08_snap.png)

Lay the front face down on a soft cloth. Press the back cover down one side at a time with
both thumbs until all eight hooks click audibly into place, two each at the top, bottom, left
and right. One side at a time is easier than all eight at once. Afterwards, the back cover lies
flat all around.

## Step 9: Switch On

![Finished](images/assembly.png)

Slider up: the display turns on. Charge through the USB-C socket at the bottom right (seen from
the front); the UART port is at the bottom left. Press BOOT and RESET with a paper clip through
the two pinholes above the slider.

## Opening

The hooks are PLA, so do not pry them by force. Push the hooks inward one at a time with a
paper clip through the eight windows in the wall, and at the same time lift the back cover at
the notch on the bottom edge with a coin or your fingernail, one side at a time. Then pull the
slider out before you take out the board.
