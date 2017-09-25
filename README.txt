Name: Bijan A. Hamidi
Date: Sept 24, 2017
Email: bhamidi@csu.fullerton.edu

Description: This is the camera dolly adjustment to the hello_glsl project.  The first change I had made to the program was located in the render() function.  I had added in conditional statements to check when one of the desired keys had been pressed ('O', 'L', 'K', ';'). I have also written functions for cameraForward(), cameraBack(), cameraPanLeft(), and cameraPanRight().  

I had also changed the if statement for when 'R' was pressed and added initCenterPosition() to reset the position of the camera. 

For moving the camera forward I had used GLM's translate function to create a translation matrix.  The input for this translate function was a hard coded vec3(0,0, -0.05).  As the camera was resting I had thought to move it along with changes to the Z axis.  I then converted the eyeposition from vec3 to vec3 placing a 0 as the new attribute.  With eyeposition as a vec4 I was now able to multiply this with the translation matrix to get the new eyePosition as a vec4.  I then converted the vec4 back to a vec3 and set it equal to eyePosition to move the camera forward.

Moving the camera backwards was an identical operation as moving it forward, however the translation function's vec3 was (0,0,0.5) to move in the opposite direction.

For camera panning left/right I had also used a similar function to the two previous but with 2 differences.  The translation vec3 had changes to the x axis rather than the z as vec3(+-0.05, 0, 0). The other change I had made was instead of calculating the translation on eyeposition I had done it on the centerposition.  I was thinking about panning the camera as walking around a focal point rather than turning a head.  I just wanted to try something different but the results between the two were almost similar.  

I have issues with the current implementation as the camera translation functions become inverted once the origin is crossed.  I attempted to remedy this by calcuating the gaze vector and multiplying this with the vec3 in the translation function but it ended up causing more issues than it had solved.  