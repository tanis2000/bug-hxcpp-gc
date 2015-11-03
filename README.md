# Demonstration of a bug in hxcpp's GC

Make sure that you have both Lime and hxcpp instaled. (tested with hxcpp 3.2.188)

Run lime update ios
Open the generated project in XCode
Run it on a real iOS device
If you run the Instruments profile (CMD+I) and select "Leaks" as template you will be able to see all of the calls to hx::GlobalChunk::pushJob. Each allocates 256 bytes and they never get collected.
