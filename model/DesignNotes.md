# CAD Models and Design Notes

This folder contains links to my Onshape models and notes on how I designed each die. I am documenting the modeling process, the problems I ran into, and the changes I made to get each model working.

| Die | Status | Onshape Model |
|---|---|---|
| D4 | Complete | [View Model](PASTE_D4_LINK_HERE) |
| D6 | Complete | [View Model](PASTE_D6_LINK_HERE) |
| D8 | Complete | [View Model](PASTE_D8_LINK_HERE) |
| D10 | Complete | [View Model](PASTE_D10_LINK_HERE) |
| D12 | Planned | — |
| D20 | Planned | — |

## D4 — Tetrahedron

### Design Process

I initially struggled with creating the geometry for the tetrahedron because I wasn't sure how to construct the shape in Onshape. I eventually discovered the loft feature, which allowed me to connect different parts of the geometry and create the four-sided die.

After creating the main shape, I worked on adding numbers to the faces by creating number geometry and using extrude-remove to engrave it into the die.

### Challenges and Solutions

**Constructing the geometry**

At first, I didn't know which features to use to create the tetrahedron. Discovering lofts gave me a way to connect the geometry and form the shape. This also gave me experience that I could use when modeling the other dice.

**Number engraving**

The number shapes had different dimensions and weren't symmetrical. When I cut the numbers into the die, some of the cutouts extended far enough to intersect with numbers on other faces, damaging the model.

I reduced the engraving depth to prevent the cutouts from reaching the other sides. I also decided not to apply fillets to the number cutouts because I wanted to avoid introducing additional complications.

### What I Learned

I learned how useful lofts can be for constructing geometry that is difficult to create with simpler features. I also learned that number placement and engraving depth need to be considered alongside the shape of the die itself.

---

## D6 — Cube

### Design Process

The basic cube geometry was straightforward to create. I made two versions of the D6: one with dots and another with numbers.

For the dotted version, I used extrude-remove to create the indented dots. I then applied fillets to round the edges of the engravings instead of leaving them sharp.

For the numbered version, I used Onshape's text feature to place numbers on the faces and created cutouts from the text.

### Challenges and Solutions

**Creating the numbered version**

Initially, I spent some time figuring out how to add text to the model. I eventually discovered Onshape's text feature, which made placing numbers much easier.

However, the numbers had different proportions, so using a single font did not always give me the appearance I wanted. I experimented with different fonts to find one with more consistent and symmetrical-looking dimensions.

**Applying colors**

Figuring out how to apply colors to the model was another challenge. I had to explore how to change the appearance of the model rather than focusing only on its geometry.

### What I Learned

The D6 gave me experience with both subtractive features and fillets. It also helped me become more familiar with Onshape's text and appearance tools.

---

## D8 — Octahedron

### Design Process

After working with lofts on the D4, I had a better idea of how to approach the D8's geometry. I essentially created two tetrahedral sections connected at their bases to form the eight-faced octahedron.

Adding the numbers followed a similar process to the previous dice. I used the text geometry to position the numbers and then engraved them into the faces.

### Challenges and Solutions

**Number cutouts intersecting**

I ran into the same problem that I had with the D4. Because the number shapes were not symmetrical in their dimensions, deeper extrude-removes could intersect with cutouts on other faces. This made the model messy and could compromise the geometry.

Instead of changing the overall shape of the die, I reduced the engraving depth to less than 1 mm. This kept the number cutouts shallow enough to avoid the intersections I had encountered.

### What I Learned

The geometry was easier to construct because I could reuse what I had learned from the D4. However, the numbering process showed me that a feature that works on one face can still cause problems elsewhere on a small, multi-faced object.

---

## D10 — Pentagonal Trapezohedron

### Design Process

The D10 was the most difficult die for me to model because I initially struggled to figure out how to construct its geometry in Onshape.

I started by creating two identical, congruent pentagonal bases at different heights. I rotated one base by 36° relative to the other so that its vertices would fall between the vertices of the first base. This staggered arrangement established the geometry for the middle section of the die.

I then worked out how to create the apex points and connect them to the pentagonal bases to form the kite-shaped faces of the D10.

My first approach was to use lofts to connect the apexes and pentagonal bases. However, this created unwanted dividing edges across the kite-shaped faces. These edges split the faces into smaller sections and prevented me from sketching on the kite faces as I intended.

I eventually switched to a different approach using Onshape's 3D Spline, Fill, and Enclose features.

### Challenges and Solutions

**1. Finding a way to construct the shape**

My initial loft-based approach did not produce the face structure I needed. The unwanted dividing edges were especially problematic because I needed each kite-shaped face to work as a surface for number placement.

I decided to build the geometry from its edges instead. I used 3D Spline to connect the vertices and create the skeleton of the shape. I found that connecting two points at a time produced straight segments, while adding more points could make the spline curve.

I then used Fill to create the faces between the edges and Enclose to turn the resulting geometry into a solid.

**2. Getting the faces to accept sketches**

Even after creating the solid, I ran into another problem: Onshape would not let me create sketches on the kite-shaped faces.

I investigated the geometry using the Plane feature. I selected three points on one kite face—the apex and two points from the first pentagonal base—to define a plane. I then checked the position of the corresponding point on the second base and found that it was offset from that plane.

This indicated that the four vertices of the kite were not all coplanar, meaning the face was not perfectly flat. That explained why I was having trouble using the face for a sketch.

**3. Finding the correct offset**

To solve the problem, I adjusted the offset between the two pentagonal bases. After each adjustment, I checked how closely the point on the second base aligned with the plane defined by the other three vertices.

I continued until the fourth point was effectively on the same plane. The final offset I settled on was **1.689231 mm**.

This adjustment made the kite-shaped faces sufficiently planar for the sketching operation to work.

**4. Adding the numbers**

Once Onshape accepted sketches on the faces, I was able to move on to the numbering. I created a construction sketch to help position each number at the desired location on its face.

This approach was similar to the numbering process I had used on the earlier dice, but getting the face geometry correct was a necessary step before I could do it successfully.

### What I Learned

The D10 taught me that creating a solid shape is not always enough. The geometry also needs to have the right structure for later operations, such as sketching and engraving.

I learned to investigate the geometry using reference planes and individual vertices rather than repeatedly trying the same feature. Changing the construction method and checking whether the faces were planar ultimately allowed me to continue with the model.

---

## D12 — Dodecahedron

**Status:** Planned

### Design Notes

I will document the modeling approach, challenges, and solutions here when I begin creating the D12.

---

## D20 — Icosahedron

**Status:** Planned

### Design Notes

I will document the modeling approach, challenges, and solutions here when I begin creating the D20.
