syntax = "proto3";

package video;

message VideoMetadata {
  string video_id = 1;
  string title = 2;
  string description = 3;
  string user_id = 4;
  string upload_date = 5;
  string video_url = 6;
  repeated string tags = 7;
}

message VideoProcessingStatus {
  string video_id = 1;
  enum Status {
    QUEUED = 0;
    PROCESSING = 1;
    PROCESSED = 2;
    FAILED = 3;
  }
  Status status = 2;
  string message = 3;
}

message VideoUploadRequest {
  string title = 1;
  string description = 2;
  string user_id = 3;
  bytes video_data = 4;
  repeated string tags = 5;
}

message VideoUploadResponse {
  string video_id = 1;
  string message = 2;
}

message VideoRetrievalRequest {
  string video_id = 1;
}

message VideoRetrievalResponse {
  VideoMetadata metadata = 1;
  string video_url = 2;
}

service VideoService {
  
  rpc UploadVideo(VideoUploadRequest) returns (VideoUploadResponse);

  rpc GetProcessingStatus(VideoRetrievalRequest) returns (VideoProcessingStatus);

  rpc GetVideoMetadata(VideoRetrievalRequest) returns (VideoRetrievalResponse);
  
}
