## OpticalFlow-FeatureExtraction
Computer Vision on Videos

### Face and Hands tracking with Use of the Lucas-Kanade Optical Flow Method

  1. **Detection**
     - **1<sup>st</sup> step**: The YCbCr color space is used, removing the information
       of the Y luminosity and keeping the Cb and Cr channels that describe its identity
       color. Skin color is modeled with a two-dimensional Gaussian distribution: 

      
       $$P( \textbf{c} = skin) = {1 \over { \sqrt{ \lvert Σ \rvert \left(2π \right) ^ 2 }}}  e^{-{ 1 \over 2 } \left( \textbf{c} - \textbf{μ} \right) Σ ^ {-1} \left( \textbf{c} -\textbf{μ} \right) ^ {'}}$$
       
       where c is the vector of Cb and Cr values for each point (x, y) in the image. 
       The Gaussian distribution is trained by computing the 2 × 1 mean vector 
       $$µ = [µCb, µCr]^T$$ and the 2 × 2 covariance matrix Σ from the skin samples given in 
       the file skinSamplesRGB.mat in RGB format. The binary skin detection image is derived 
       from the probability image $$P(c(x, y) = skin)$$, ∀ (x, y) with thresholding.
       
     - **2<sup>nd</sup> step**: It is required a morphological processing of binary skin image. 
       Specifically, the holes that appear will be covered by applying an opening with a very small 
       structural element and closing with a large structural element. Finally, you will create 
       three rectangles that will surround the areas of interest-skin (bounding boxes).
  
  2. **Tracking**
      - Implementation of Lucas Kanade Algorithm
      - Implementation of Multiscale Lucas Kanade Algorithm
      
  3. **Evaluation**
      - Evaluation of both with given dataset
      - Production of video of skin tracking and the optical flow
