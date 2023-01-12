First up, fire the IMG_0917.jpeg in exiftool, which will give us majority of data required 
like coordinates(latitude, longitude, time when the photo was taken, serial number).

<img width="437" alt="lat_long" src="https://user-images.githubusercontent.com/98313379/212198196-bd40c4d2-34d2-4feb-9bfa-7ecc70734e89.png">
<img width="348" alt="ser_num" src="https://user-images.githubusercontent.com/98313379/212198201-9fb5e398-abda-4c5b-8d87-dd23bb642646.png">
<img width="399" alt="time_cap" src="https://user-images.githubusercontent.com/98313379/212198203-51be7b27-81b6-4d57-ac43-949a9ccc1d1f.png">

As the flag format required us to truncate latitude and longitude upto 2 decimal places, we get 37.74_-119.59 as the first two parts of the flag irisctf{latitude_longitude_epochtime_serialnum_secret} and 392075057288 as the fourth part.

For calculating epochtime, open up https://www.timeanddate.com/ to find the difference between UTC and Los Angeles TimeZone(as the coordinates tell us the location of photo), which came out to be UTC-7.So, we have to add 7 hrs to 10:04:56 before calculating epochtime, which comes out to be 17:04:56. Now, we will find the epochtime on https://www.epochconverter.com/ by giving the values 2022, 27th of August, 17 hrs, 4 minutes, 56 seconds.

<img width="667" alt="epochtime" src="https://user-images.githubusercontent.com/98313379/212199737-d47c37fd-abcf-4292-8fc6-a6b787d5af7e.png">

So, our 3rd part of flag is 1661619896.
 For the secret flag, open https://hexed.it/ and change the header of the image as follows:
 <img width="671" alt="repair" src="https://user-images.githubusercontent.com/98313379/212200172-92c71f95-9775-439e-890f-070506626466.png">
 
Opening it, we get the secret part of flag(5th part, i.e. exif_data_can_leak_a_lot_of_info}
<img width="1157" alt="secret" src="https://user-images.githubusercontent.com/98313379/212200258-5c7a5106-925a-4dca-8cb0-b80f5aac20c9.png">

Hence, our flag comes out to be: irisctf{37.74_-119.59_1661619896_392075057288_exif_data_can_leak_a_lot_of_info}
 
