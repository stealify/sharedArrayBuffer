# sharedArrayBuffer
This is a Core Component when it comes to situations where you interop between diffrent languages.

## When to use?
As rule of thumb interOp a FFI call is Fast but Custom Typed Protocols that work on sharedArrayBuffers that contain most of the time u8 int

when you use stdio charset based like stdin this should also work as x-user-defined charset of UTF8 maps to the Private area you can drop 0xFF first and get raw bytes
without switching the stdio to binary mode but when you switch it to binary you can save time no need to drop 0xFF 

## Special Case Windows C Runtime
https://docs.microsoft.com/en-us/cpp/c-runtime-library/crt-library-features?redirectedfrom=MSDN&view=msvc-170#what-problems-exist-if-an-application-uses-more-than-one-crt-version

the importent part is exactly referencing what stealify is about.

You can avoid many of these issues by using Application Binary Interface (ABI) technologies instead, as they're designed to be stable and versionable. Design your DLL export interfaces to pass information by value, or to work on memory that is passed in by the caller rather than allocated locally and returned to the caller. Use marshaling techniques to copy structured data between executable images. Encapsulate resources locally and only allow manipulation through handles or functions you expose to clients.

on cli clients for debuging and UX Frindly ness always show dry run information and let the user choose to suppress that via -y or -silent the default should always be debug. 
