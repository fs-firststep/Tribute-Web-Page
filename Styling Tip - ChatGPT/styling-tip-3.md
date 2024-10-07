why we should use  {overflow: hidden;} in image container ?

Using `**overflow: hidden;**` in the `.image_container` is often important when dealing with images or other content inside a container. Here's why:

### 1. **Prevent Overflowing of Content:**
   - **Purpose**: The `overflow: hidden;` ensures that any part of the image that exceeds the boundaries of the `.image_container` is clipped or hidden. This keeps the content neatly contained within the container’s dimensions.
   - **Without `overflow: hidden;`**: If the image inside the container is larger than the container's width or height, parts of the image may "overflow" and appear outside the intended area, potentially breaking the design layout.

### 2. **Maintain Image Aspect Ratio:**
   - **Fixed Aspect Ratio**: When the image has different dimensions than the container (e.g., the container is square, but the image is rectangular), `overflow: hidden;` helps to cut off the excess part of the image that spills out of the container, thus forcing the image to fit within a certain frame.
   - This is especially useful for maintaining a consistent layout where you want all images to appear as the same size, regardless of their original dimensions.

### 3. **Responsive Designs:**
   - **Uniform Image Cropping**: In responsive layouts, if the image container resizes based on screen width or height, `overflow: hidden;` ensures that the image adjusts or crops itself to fit within the container's boundaries without breaking out of the design.
   - This is useful when you’re applying styles like `border-radius`, as it ensures the content inside respects the rounded corners.

### 4. **Avoid Layout Issues:**
   - **Prevent Layout Shifting**: If an image's content is allowed to overflow the container, it may cause unintended layout shifting or content overlapping, especially in smaller screens or dynamic/responsive designs. `overflow: hidden;` helps prevent this.

### Example in Your Case:
In your `.image_container`, you set dimensions (`width: 300px; height: 320px;`) and have applied a `border-radius: 30%`, making the image container a rounded shape. If the image inside is larger or doesn't match this aspect ratio, it could overflow and break the rounded look.

By adding `overflow: hidden;`, the extra part of the image will be cut off, ensuring the image stays within the boundaries and maintains a clean, consistent appearance.

```css
.image_container {
    border-radius: 30%;
    width: 300px;
    height: 320px;
    overflow: hidden; /* This clips any part of the image that exceeds container dimensions */
}
```

### When You Should Use `overflow: hidden;`:
- **Clipping content** that exceeds the container size (like images or other elements).
- **Creating specific shapes** for images, like circles or rounded rectangles.
- **Ensuring layout consistency** in cases where content inside the container might be larger or misaligned.

### When You Might Not Need It:
- If the image fits perfectly within the container and doesn't need to be clipped.
- If you want the image to overflow and be partially visible outside the container for some creative effect.

Let me know if you have any further questions or if you'd like to see examples!