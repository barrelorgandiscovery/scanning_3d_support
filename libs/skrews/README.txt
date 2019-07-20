                   .:                     :,                                          
,:::::::: ::`      :::                   :::                                          
,:::::::: ::`      :::                   :::                                          
.,,:::,,, ::`.:,   ... .. .:,     .:. ..`... ..`   ..   .:,    .. ::  .::,     .:,`   
   ,::    :::::::  ::, :::::::  `:::::::.,:: :::  ::: .::::::  ::::: ::::::  .::::::  
   ,::    :::::::: ::, :::::::: ::::::::.,:: :::  ::: :::,:::, ::::: ::::::, :::::::: 
   ,::    :::  ::: ::, :::  :::`::.  :::.,::  ::,`::`:::   ::: :::  `::,`   :::   ::: 
   ,::    ::.  ::: ::, ::`  :::.::    ::.,::  :::::: ::::::::: ::`   :::::: ::::::::: 
   ,::    ::.  ::: ::, ::`  :::.::    ::.,::  .::::: ::::::::: ::`    ::::::::::::::: 
   ,::    ::.  ::: ::, ::`  ::: ::: `:::.,::   ::::  :::`  ,,, ::`  .::  :::.::.  ,,, 
   ,::    ::.  ::: ::, ::`  ::: ::::::::.,::   ::::   :::::::` ::`   ::::::: :::::::. 
   ,::    ::.  ::: ::, ::`  :::  :::::::`,::    ::.    :::::`  ::`   ::::::   :::::.  
                                ::,  ,::                               ``             
                                ::::::::                                              
                                 ::::::                                               
                                  `,,`


https://www.thingiverse.com/thing:3131126
OpenScad library. Threads for screws and nuts V1 by Cuiso is licensed under the Creative Commons - Attribution license.
http://creativecommons.org/licenses/by/3.0/

# Summary

<h3>This is an OpenSCAD library to include threads for screws and nuts in your own designs.</h3>

This library is focused to provide simple functions with preset parameters by default,
and not to be too demanding in CPU consumption neither in previsualizacion nor in rendering

This library has been tested printing on PLA with 0.1 layer. Except for smaller diameter
threads layers greater than 0.1 should work well.
Diamaters tested between 3mm and 10mm, but you can use any diameter of your choice. 

Shape of the threads are similar (but not equal) to ISO METRIC threads.
Some tests have been done using screws and nuts printed with this library in
combination with screws and nuts of metal with acceptable results. However, they have
not been exhaustive tests.

<h3>Included:</h3>
Library file named threads-library-by-cuiso-v1.scad
A file with examples of use named examples.scad

For use this library you can put the file threads-library-by-cuiso-v1.scad in the same directory of your proyect and put the line use <threads-library-by-cuiso-v1.scad> in your own .scad file

You can also open it in customizer to obtain a screw and / or nut thread of the desired size that you can include in your own designs.

<h3>AVAILABLE FUNCTIONS:</h3>

<h3>BASIC FUNCTIONS (USING PREDEFINED PARAMETERS):</h3>

<h3>thread_for_screw(diameter, length);</h3>
    Generates a screw thread of the diameter indicated by the "diameter" parameter and of the length indicated by "length".
This function uses standard pitch values depending on the diameter specified.
    diameter: Free value, in milimeters.
    length: Free value, in milimeters.
    
    Example:
    thread_for_screw(diameter=10, length=30);

<h3>thread_for_nut(diameter, length, usrclearance=0);</h3>
    Generates a nut thread of the diameter indicated by the "diameter" parameter and of the length indicated by "length".
This function uses standard pitch values depending on the diameter specified.
    The generated thread can be subtracted from any element of your design using the operator "difference()", thus obtaining a thread where a screw will fit.
    This function uses standard clearance for adjustment between screw and nut depending on the diameter specified.
    diameter: Free value, in milimeters.
    length: Free value, in milimeters.
    usrclearance: (optional) If the screw fits too tight on the nut you can specify a positive correction value (try 0.1 for example).
    If the screw fits too loose in the nut you can specify a negative correction value (try -0.1 for example).
    
    Example:
    thread_for_nut(diameter=10, length=20);
    

<h3>MORE AVAILABLE FUNCTIONS (WITH ADDITIONAL PARAMETERS):</h3>

<h3>thread_for_screw_fullparm(diameter, length, pitch, divs=50);</h3>
    Generates a screw thread of the diameter indicated by the "diameter" parameter and of the length indicated by "length", 
with pitch indicated by "pitch", and a resolution indicated by "divs". 
    This function allows you to specify a non-standard "pitch" value.
    diameter: Free value, in milimeters.
    length: Free value, in milimeters.
    pitch: Pitch value.
    divs: (optional) you can obtain more or less resolution with parm. Higher values for more resolution (and more rendering time). Default value is 50.
        
    Example:
    thread_for_screw_fullparm(diameter=10, length=30, pitch=2, divs=60);

<h3>thread_for_nut_fullparm(diameter, length, usrclearance=0, pitch, divs=50, entry=1);</h3>
    Generates a nut thread with additional parameters:
    diameter: Free value, in milimeters.
    length: Free value, in milimeters.
    usrclearance: (optional) If the screw fits too tight on the nut you can specify a positive correction value (try 0.1 for example).
    If the screw fits too loose in the nut you can specify a negative correction value (try -0.1 for example).
    pitch: Pitch value.
    divs: (optional) you can obtain more or less resolution with parm. Higher values for more 
resolution (and more rendering time). Default value is 50.
    entry: (optional) By default, the nut threads include a wider entrance area at the beginning and end to facilitate the introduction of the screw and minimize "elephant foot" problems.
    Specify 1 in entry to use these zones and 0 to not use them.
    
    Example:
    thread_for_nut_fullparm(diameter=10,length=20,usrclearance=0.1,pitch=1.5,divs=60, entry=1);

More details into library file.
This library has been useful for me, I hope it can be useful for you too.

<h3>Change log:</h3>
- 03/10/2018 Changed documentation of function thread_for_nut(diameter, length, usrclearance=0) (documentation now includes parameter usrclearance)