# kvazaar
An open-source HEVC encoder

# modification:
  - support tile priority: add `tiles_encoding_priority` to `kvz_config` and pass the encoder to `threadqueue_queue_t`, when a ready job is push into the `threadqueue_queue_t`, insert it according to its priority``
  ```c
    kvz_encoder* encoder = threadqueue->encoder;
	  int32_t* priority_arr = encoder->control->cfg.tiles_encoding_priority;
	  for (int i = 0; priority_arr[i] >= 0; i++) {
		  if (priority_arr[i] == tile_id) {
			  state->encoding_priority = 1;
		  }
	  }
  ```
