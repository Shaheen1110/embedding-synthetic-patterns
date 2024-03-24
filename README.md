# embedding-synthetic-patterns

This Python code provides functionalities for processing raw image data, including loading, embedding patterns, comparing images, and displaying heatmaps of dissimilar blocks.

## Step-by-Step Usage

### 1. Load Raw Image Data

- Use the `np.fromfile` function to load raw image data from a file.
- Specify the file path and data type (`dtype`) as `np.uint16`.

   ```python
   file_path = '/path/to/your/raw/image/file.raw'
   with open(file_path, 'rb') as file:
       raw_data = np.fromfile(file, dtype=np.uint16)
   ```

### 2. Embed Patterns into Images

- Use the `embed_images` function to embed patterns into images.
- Provide the image data, pattern data, position indices (`row_index` and `col_index`), and size (`size_height` and `size_width`) of the pattern.

   ```python
   embed_images(image_data, pattern_data, row_index, col_index, size_height, size_width)
   ```

### 3. Compare Images Based on Block-Level Statistics

- Use the `calculate_block_dissimilarity` function to compare images based on block-level statistics.
- Provide two blocks of image data (`input_block` and `modified_block`) to calculate the dissimilarity.

   ```python
   calculate_block_dissimilarity(input_block, modified_block)
   ```

### 4. Display Heatmaps of Dissimilar Blocks

- Use the `plot_heatmap` function to display heatmaps of dissimilar blocks for each comparison.
- Provide the list of dissimilar blocks (`dissimilar_blocks`) and a title (`title`) for the heatmap.

   ```python
   plot_heatmap(dissimilar_blocks, title)
   ```

## Example

```python
# Load raw image data
file_path = '/path/to/your/raw/image/file.raw'
with open(file_path, 'rb') as file:
    raw_data = np.fromfile(file, dtype=np.uint16)

image_width = 1920
image_height = len(raw_data) // image_width
image_data = raw_data[:image_width * image_height].reshape((image_height, image_width))

# Display the image
plt.imshow(image_data)
plt.show()
```



---

In the example, replace `/path/to/your/raw/image/file.raw` with the actual path to your raw image file.
