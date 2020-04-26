->This function returns the same values as the original "ginput". However, mt_ginput function now asks for a second input:

- function [out1,out2,out3] = mt_ginput(arg1,handles) 
- %%% Adapted by Gorka Zubia Garea 10/06/2019

-> This second input is asks for a GUI's "handles".

-> In the mt_ginput function "handles.edit_tini" and "handles.edit_tfin" edit boxes are used to print the current value of the mouse/cursor.

-> Handlers to edit boxes have been used but can be used for any kind of text recipients.

-> Feel free to change the names of your text recipients to the ones you desire by modifying their names, in the mt_ginput function's lines 75 and 233, respectively. 
------> Line 75: 
------------------set(fig,'WindowButtonMotionFcn',{@mouse_trace,handles.edit_tfin}); 
------------------> Instead of "handles.edit_tfin" insert your desired text recipient. 
------------------> The same applies for the line 233, but with handles.edit_tini instead.

-> This way, once you have activated the mt_ginput function, it starts to trace your mouse/cursor position in the current figure, with the "full crosshair" pointer.
---------> For example: 
-----------------------------[x,~] = mt_ginput(2,handles); 
%%%%%%%%%%% When that line executes, mt_ginput will start showing in the edit_tini editbox your mouse/cursor x position in the figure until you click. After that click, the edit_tini editbox value fixes to the position clicked. Then, one more click is needed to terminate the function, like with the original ginput, but now it automatically starts tracing your mouse/cursor position in the edit_tfin editbox until you click again. That mouse/cursor position will stay fixed in your edit_tfin editbox and the function will terminate.

-> It will stop tracking your mouse position when you click
