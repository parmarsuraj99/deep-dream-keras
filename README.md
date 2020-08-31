# deep-dream-keras
Deep Dream implementation inspired from official keras code.

Script to keep dreaming in a loop and creating a video from the frames.

### Example

- On one image

    ```python
    python src/dream.py \
        --src_img inputs/aus.jpg \
        --result_img results/aus_dream.jpg
    ```

- Keep Dreaming
  
  ```python
  python src/keep_dreaming.py \
    --src_img inputs/aus.jpg \
    --directory dream_seq \
    --iterations 100 \
    --overwrite_save_dir false
  ```
