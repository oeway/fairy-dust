# Fairy Dust: A point cloud viewer for single-molecule localization microscopy data
## Technical details
A file loader for tab separated location data text files: parsing each column to a Float32 array, find the minimum, maximum, and mean value. Then create a strided array that can be used for texture data that contains vertex data for a point cloud. The heavy lifting for the parser happens async in a Web Worker, and the strided arrays come in chunks of an adjustable length. The location data is stored in the float32 rgba values of a texture of 512 * 512 = 256K vertices. In interactive view finding, the renderer throttles the number of displayed chunks down until an interactive rate of 24 frames per second is reached. As soon as the camera stands still, the whole point set will be drawn.

## Acknowledgements

The FairyDust plugin used in ShareLoc.XYZ is adapted from the Fairy Dust viewer developed by [Felix Woitzel](https://twitter.com/flexi23)(in collaboration with [Christophe Leterrier](https://twitter.com/christlet)).
