# The main entities typically defined in a video processing system design.

The main entities include:
User (the person uploading),
Video (source and processed versions),
Thumbnails,
Audio tracks (separate from video),
Metadata (title, resolution, and other properties),
and Manifest (determines bit rate and resolution for different clients (mobile, tablet, desktop, tv)).

# Uploads should not be assumed successful because they can fail due to various reasons,

especially with large video files. Issues include client errors, slow internet connections that can't handle the upload, or long upload times that may be interrupted.

The system needs to handle recovery from failures and notify users when uploads complete successfully.

# A manifest

is a file that determines the bit rate and resolution that a client plays based on the device characteristics.

It's computed on the back end and is different for each user. 

A manifest is necessary because showing the highest resolution to all devices would be wasteful 

— for example, a phone can't distinguish 4K from HD due to its small screen size. 

The manifest ensures each device receives the best appropriate resolution for that specific device rather than always sending the highest quality.


## The flow of the video uploading system.

Video Upload Process:
- User initiates video upload
- User receives notification upon successful upload
- System processes the video
- User receives notification upon completion or failure of processing


### When designing a video upload system, why is it beneficial to separate metadata storage from video blob storage?

Blob storage is more optimized for video and audio files, while databases are better suited for text data like metadata. 

Additionally, keeping the system stateless by writing metadata to a database prevents problems where uploads complete but have no associated metadata, which would create orphaned files that are useless and cannot be properly managed or deleted.

### Why is it important to understand the user flow before diving into technical implementation details when designing a system?

Understanding the user flow helps identify what the actual problems and bottlenecks will be in the system. 

Without understanding the domain and workflow first, you risk overdesigning one particular part while missing critical 
components, or choosing optimizations that don't address the real constraints of the system.

Understanding user flow helps identify the actual problem domain and potential bottlenecks before over-engineering specific components. 

Without understanding what the user is trying to do, you might design for the wrong constraints (like scaling to a million users) when the actual bottleneck is elsewhere, such as the database or processing pipeline.

### In a video processing system, why should the source video storage contain raw, unprocessed video rather than immediately extracting metadata and other components?

Keeping the source video storage as raw as possible maintains a clean separation of concerns. 

The processing service should be responsible for pulling apart the metadata, thumbnails, and separating audio/video during the processing stage. 

This approach ensures the source remains pristine and processing logic is centralized in the appropriate service.

### Why might you create separate services for different aspects of a video processing system?

Creating separate services (microservices) helps break down complex workflows into manageable components. 

For example, a notification service can handle alerting clients when uploads complete, 
while a processing service handles video transcoding. 

This separation makes the system easier to reason about, scale independently, and maintain stateless operations.

