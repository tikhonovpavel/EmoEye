raw_data - raw files

prep_data - prepared files. 
In each folder (0, 1, 2, … etc.) csv files corresponding to eye-trackings and biometric data
 For example, 0_dog 7_4_6.csv is a response to the first picture in the session, “dog 7.jpg”, participant reported 4 on arousal and 6 on valence scales.

TIME - time sec from the beginning of the recording
FPOGX, FPOGY - Fixation Point-Of-Gaze (X, Y coordinates, from 0 to 1 with outliers if person looks outside of the screen)
FPOGID - index of the fixation point
FPOGV - is FPOG valid? if eyes were not detected or smth happened - this column has some zeros
LPMM, RPMM - left and right eye pupil diameter in millimeters
LPMMV, RPMMV -  is LPMM/RPMM valid?
GSR - galvanic skin response
GSRV - is GSR valid? 
HR - heart rate
HRV - is HR valid?
Image - image shown
Arousal, Valence - response of the participants 

prep_data.zip - zipped prep_data

final_emotion.ipynb - my final solution on keras

multimodal_nn.jpg - my final architecture
