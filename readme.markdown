# feed.proto

[JSON Feed][1] is a syndication format specification that targets JSON as the serialization format.  feed.proto is a parallel format that mirrors JSON Feed as much as possible, using protocol buffers instead of JSON as the serialization format.

## But, why?

There is no broad ambition for this project.  This is provided merely as an exercise.

That said, there are several reasons to consider using protobuf as a serialization format.

Protobuf is a more efficient format than JSON.  The data is more compact and the serialization phase is often much faster with a lower memory overhead compared to JSON.  Consuming protobuf feeds should be faster and more efficient than consuming equivalent JSON feeds.

Protobuf objects can also be created from JSON.  You could therefore continue to consume JSON, but use the protobuf objects as a simple, typed data representation of the JSON.

## Drawbacks

The most recent specification of protocol buffers does not store unknown or unexpected data.  Therefore, some of the data that *could* be provided under JSON Feed will be ignored or lost when using feed.proto.  This is most likely publisher extensions.  They are not required by the JSON Feed spec and can be safely ignored, but this loss is regretable.

## Contact

For questions, complaints, or suggestions, please contact:

[Grayson Hansard](mailto:grayson.hansard@gmail.com)  
[@Grayson](http://twitter.com/Grayson) ([micro.blog](https://micro.blog/Grayson))

[1]: https://jsonfeed.org