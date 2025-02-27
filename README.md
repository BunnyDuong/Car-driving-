# Autonomous car driving
In this project, I'm using data from https://www.dropbox.com/scl/fo/uscpkxvmwb4hx3tlm0wo7/AM1NFQ4k6zjB3wkGTEnDG5Y?rlkey=4nf2fil3dwkxbjykxlsmdufuf&e=1&dl=0 which contains an excel file and an image file. The model built based on NVIDIA paper (https://arxiv.org/pdf/1604.07316v1.pdf).

The project is about building a CNN model that computes steering angle as output, it follows those steps:
1. Separate data into train and validation samples
2. Augmentation with techniques:
  - Random Flip
  - Random salt and pepper noise
  - Random translate
  - Random shadow
  - Random brightness
  - YUV transformation
  - Crop
3. Driving-error data: to make the vehicle driving on track, we use not only center-lane driving data but also left and right-lande driving of the road so that our car can correct its mistake whenever it's off track
4. Generate images for each batch using lazy generator so that our RAM will not be exceeded
5. The CNN models are built following the paper but in this project, I used some dropout layer after dense-layers as I realized that the model is overfitting as the training set has a low mean square score but high in the validation set
  <img width="305" alt="Screenshot 2025-02-12 115501" src="https://github.com/user-attachments/assets/96e1932a-8a3f-40db-8bdf-951b25016ad7" />

  


