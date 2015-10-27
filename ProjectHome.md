FFmpeg-MSVC is an attempt to port the FFmpeg suite to Microsoft Visual Studio 2008. Almost all of the porting is done with #ifdefs leaving the original code intact. It is based on the 0.6 release of FFmpeg. Small bits and pieces have been taken from other attempts to port FFmpeg.

The main changes revolve around differences between the GCC compiler and the MSVC compiler. Microsoft hasn't paid much attention to the base C compiler in it's product. This makes compiling open source projects more and more cumbersome. FFmpeg makes use of the C99 standard, even though it's now over 10 years old, Microsoft has hasn't seen the need to bring over the new features.

Example compiler problems:
  * Variable length arrays
    1. int x[some\_non\_constant](some_non_constant.md);
  * Designated initializers and compound literals
    1. struct pos = {0, .z = 10 };
    1. t = (struct timeval) { .tv\_usec = n };
  * Inline AT&T style assembly vs. Intel style
  * A host of other minor differences

Current Issues:
  * Relatively untested and early in development
  * Missing encoders/decoders
  * Missing formats
  * No SIMD support (MMX/SSE,etc) so things run slow
  * ffserver has not been ported
  * Not 100% all GPL code has been compiled out

[FFmpeg home page](http://ffmpeg.org/)