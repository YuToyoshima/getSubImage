# getSubImage
#
# This code is to get an array of pixel values of sub region in large Tiff image that saved by ImageJ/Fiji.
# This code is memory-efficient (VirtualStack in ImageJ)) and utilizes cache (MappedByteBuffer in Java).
# 
# Usage of Java version in Matlab:
#  0. (Add ImageJ/Fiji classes to javaclasspath in matlab.)
#  1. (Add MyFileInfoVirtualStack.class to javaclasspath in matlab.)
#  2. Create an instance of MyFileInfoVirtualStack in matlab.
#     > mfivs = MyFileInfoVirtualStack(PATH_TO_IMAGE,BOOLEAN_TO_SHOW); 
#  3. Get an array of pixel values of sub region.
#     > SUB_REGION = [xstart,ystart,xend,yend];
#     > pixels = mfivs.getSubImage(FRAME_INDEX,SUB_REGION)
#  4. typecast and reshape may be needed.
#     > TYPE = 'uint8'; % type of image
#     > subimage = reshape(typecast(pixles,TYPE),SUB_REGION(3:4)-SUB_REGION(1:2)+1);
#
