video.getUploadUrl

$description
Method for creating new video and getting upload url

$params#uid
Id of user-owner of the video

$params#gid
Id of group-owner of the video

$params#file_name
The name for video

$params#attachment_type
Only for "attachment" cases

* MOVIE - video-attach from disc
* VIDEO - video-attach from camera (length restricted to 3 minutes)
* AUDIO_RECORDING - audio-attach from mic (length restricted to 3 minutes)

$params#file_size
The size of file to upload. If You don't know the size at the moment you call this method then pass 0

$params#lat
Latitude

$params#lng
Longitude

$params#cid
ID of video-channel

$params#post_form
Upload during post creation (No "Video uploaded" feed created in this case)

$additional
**Possible error codes**

|Name                   |Description                                  |
|-----------------------|---------------------------------------------|
|PARAM : FileToSmall    |File is to small (less than 16kb)            |
|PARAM : FileToLarge    |File is to large (more than 1gb)             |
|PARAM : BadFormat      |Unsupported file format                      |
|PARAM : DvdMenu        |An attempt to upload menu-file for DVD-video |