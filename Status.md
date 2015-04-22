# Summary #

Core Image Kernels have been developed and tested. Missing an encapsulating image unit.

## Details ##

The filter consists of three parts, which is necessary for an inverted error diffusion algorithm as far as I could figure out.
  1. **Prepare data** convert to grayscale, calculate initial error and make room for error term and alpha in RGB triplet
  1. **Iterate** calculate value based on errror from neighboring pixels. This must be done for each pixel, and due to the way Core Image functions, all pixels have to be re-evaluated (even those already "solved") for every other pixel.
  1. **Finish** simply make an (black & white) RGBA image again out of the data

# What's left #
The cikernels have been tested in Quartz Composer and work as expected. What's left to be done is an Image Unit which goes through the above steps. The iterations have to be equal to the number of pixels - may be lower depending on the image but no harm is done if too many iterations are performed.

I will finish this thing as soon as the magical Vacant Weekend arrives, or when enough people write concerned mails about it. Or, of course, anyone is welcome to carry the torch from here on.