# YTUpload

### Motivation

This project arose from a need to programmatically schedule youtube content. Using the UI is fine but time consuming and some sort of programmatic batch upload would be much better.

Google already has an API exposed for "normal" Youtube videos (`https://developers.google.com/youtube/v3/guides/uploading_a_video`), but internet wisdom says it's possible to upload shorts through that API if you follow Youtube's guidelines for promoting them. (`https://stackoverflow.com/questions/68537601/is-it-possible-to-upload-youtube-shorts-via-the-api`)

### Goals

1. Create a Python script that can read a configuration file to upload a batch of video files sitting in a folder.
2. Containerize the python script so a folder can be mounted and a configuration file copied in. Starting the container should copy in the config/videos, upload them to Youtube, and print log lines so that errors can be corrected/successful upload can be observed.
3. (Optional) Periodically run the container through some sort of automation (Jenkins, cron job) 

### Project Structure

`yt-upload.py` - Main Python file that will execute the uploads.

`config.json` - (User Provided) Config containing the JSON representing an upload that is read by `yt-upload.py`. Description of how it's formatted below. 

`config-example.json` - Example config.json.

`docker-compose.yml` - Docker container run config.

`Dockerfile` - Docker container config.

`videos/` - (User Provided) Video folder where items will go.

### config.json Format

TODO

### Notes/Considerations

Youtube Shorts is still in beta, so they may release an official api someday and that API will need to be added here.
