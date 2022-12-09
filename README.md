# Classifier-Based Image Renamer
Renames a directory of images based on the image class according to an ML model (using Teachable Machine). To use it:

1. Create an image classifier model using [Teachable Machine](https://teachablemachine.withgoogle.com/). You just need to drag and drop a bunch of examples of each class and it trains the model in your browser - very easy and convenient.
2. Click the "upload model" button when training completes and copy the URL that it gives you.
3. Go here: https://josephrocca.github.io/classifier-based-renamer/
4. Paste your model URL and select a directory of images to classify and rename. The class name will be prepended to the image's existing filename.

If you'd like to *delete* certain classes of images (instead of just renaming), then you can use this tool to rename the images, and then use your operating system's "search in directory" or "sort filenames alphabetically" functionality to isolate images of a particular class and then delete them. Or if you know how to use the terminal you can of course use a command like `rm classname__*`.

If you happen to be deleting frames (e.g. produced by ffmpeg) from a video, and want to rename the frames to be numbered sequentially (after deletion of some frames) so you can feed them back into ffmpeg to create a new video, then you can use [this tool](https://github.com/josephrocca/sequential-renamer) to do that. So your process would be:

1. Convert video to frames: `ffmpeg -i video.mp4 frame-%d.jpg`
2. Rename frames: https://josephrocca.github.io/classifier-based-renamer/
3. Delete frames of certain class: `find . -name 'classNameToDelete___*' -exec rm {} +`
4. Rename the remaining frames to be sequentially numbered: https://josephrocca.github.io/sequential-renamer/
5. Merge those frames back into a video: `ffmpeg -i frame-%d.jpg video.mp4`

(That's mostly a note to my future self...)
