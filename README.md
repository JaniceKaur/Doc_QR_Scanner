# Doc_QR_Scanner

Methodology 
 
Scanning a document: 
The steps that we need to follow to build this project are: 
 
1. Convert the image to grayscale 
OpenCV image processing cv2.cvtColor() method is used to change the colour of the image. More than 150 colour methods provided to change colour space. In this, we will change RGB to Gray colours space 
 
2. Reducing noise and detecting the edges in the image 
The most important part for detecting an image accurately is to remove the unnecessary noise present in it. there are many methods provided in OpenCV. Clearing noise of image with (cv2.erode, cv2.morphologyEx) and edges can be found by cv2.Canny method. 
 
3. Image thresholding and finding contours 
Thresholding helps us in archiving better result in finding Contours of image. Contours are nothing but the edges region this could be achieved by cv2.adaptiveThreshold and cv2.findContours method in OpenCV. 
 
4. Find the biggest contour area and approx poly 
Next step is to find the biggest contour and crop the image to that contour and display it. for counting the biggest contour out of all counters OpenCV provides cv2.contourArea() method and after getting the main contour we have to find the approx-poly main coordinates the image by 
(cv2.approxPolyDP, cv2.arcLength). 
 
5. Apply warp perspective to get the top-down view of the document 
The final step is to crop the image to approx-poly with cv2.getPerspectiveTransform, cv2.warpPerspective) and display it. 

![image](https://user-images.githubusercontent.com/59028457/208242072-b1a746ed-e952-4f41-b317-7a0cc8d643e3.jpeg)


Scanning a QR code: 
 
A standard QR code has the following components: 
 
1.	Quiet Zone - This is the empty white border around the outside of a QR code. Without this border, a QR reader will not be able to determine what is and is not contained within the QR code (due to interference from outside elements). 
 
2.	Finder pattern - QR codes usually contain three black squares in the bottom left, top left, and top right corners. These squares tell a QR reader that it is looking at a QR code and where the outside boundaries of the code lie. 
 
3.	Alignment pattern - This is another smaller square contained somewhere near the bottom right corner. It ensures that the QR code can be read, even if it is skewed or at an angle. 
 
4.	Timing pattern - This is an L-shaped line that runs between the three squares in the finder pattern. The timing pattern helps the reader identify individual squares within the whole code and makes it possible for a damaged QR code to be read. 
 
5.	Version information - This is a small field of information contained near the top–right finder pattern cell. This identifies which version of the QR code is being read (see “Types of QR code” below). 
 
6.	Data cells - The rest of the QR code communicates the actual information, i.e., the URL, phone number, or message it contains. 
 
7.	Error correction level- It tells about the percentage of data bytes that can be recovered. Based on the level of error correction, there can be 4 different categories. Low(7%), medium(15%), quartile(25%) and high(30%). The higher the level, the lower is the storage capacity.  


![image](https://user-images.githubusercontent.com/59028457/208242081-39d0dbed-ed98-4ccb-b297-d2ce6fb99b22.jpeg)

