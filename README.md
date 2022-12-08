# Classifier-Based Image Renamer
Renames a directory of images based on the image class according to an ML model (using Teachable Machine). To use it:

1. Create an image classifier model using Teachable Machine. You just need a bunch of examples of each class - it trains in your browser.
2. Click the "upload model" button when training completes and copy the URL that it gives you.
3. Go here: https://josephrocca.github.io/classifier-based-renamer/
4. Paste your model URL and select a directory of images to classify and rename.

If you'd like to *delete* certain classes of images (instead of just renaming), then you can use this tool to rename the images, and then use your operating system's "search in directory" or "sort filenames alphabetically" functionality to isolate images of a particular class and then delete them.
