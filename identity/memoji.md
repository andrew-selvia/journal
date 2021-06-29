# MeMoji

MeMoji are a fun way to represent yourself digitally. While officially intended for use within Messages, MeMoji *can* be used elsewhere if you're willing to be a little clever.

## Set as photo in Messages

The starting point is obviously to create your MeMoji in Messages as demonstrated in [this Apple Support video](https://www.youtube.com/watch?v=-4n7YbupSlY). For additional information, refer to [the official documentation](https://support.apple.com/en-us/HT208986). Once you've gone to the trouble to set up your MeMoji, of course, you may want to use it to represent you elsewhere. To do that, you'll need to save your MeMoji as a file.

## Save as file

The process of saving a MeMoji as a file is more involved but still achievable. [This Medium article](https://medium.com/@matheusmaus/how-to-have-your-memoji-as-your-profile-picture-cca06cdc8cbb) is worth referencing, though the guide below provides some additional tips in case you also suffer from perfectionism.

1. Navigate to [icloud.com](https://icloud.com).
2. Download the photo as described in [this article](https://medium.com/@matheusmaus/how-to-have-your-memoji-as-your-profile-picture-cca06cdc8cbb).

    ![Portrait photo extracted from icloud.com](/photos/input.png)

3. Open it in Preview.
4. Make a perfectly-square rectangular selection that fits the MeMoji similarly to how it looks in Messages. Treat this as only a rough estimate of the final size, though.
5. Set the `INPUT_FILE_NAME`, `OUTPUT_FILE_NAME`, and `LENGTH` parameters in the script below; set `LENGTH` to the rough estimate determined in the previous step. Then, run the script to crop the downloaded image to a perfect square centered on your MeMoji.

   ```shell
   INPUT_FILE_NAME=input.png
   OUTPUT_FILE_NAME=output.png
   LENGTH=430
   WIDTH=$(identify -ping -format "%w" $INPUT_FILE_NAME)
   HEIGHT=$(identify -ping -format "%h" $INPUT_FILE_NAME)
   X=$(echo "scale=2;($WIDTH-$LENGTH)/2" | bc)
   Y=$(echo "scale=2;($HEIGHT-$LENGTH)/2" | bc)            
   convert $INPUT_FILE_NAME -crop ${LENGTH}x$LENGTH+$X+$Y $OUTPUT_FILE_NAME
   ```

   ![Square photo centered on MeMoji](/photos/output.png)

Now, all that's left to do is replace all your profile photos with the output image. If only that could be automated so easily...
