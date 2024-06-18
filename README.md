# Estimation_hm

Estimation sheet from hm using script



Excel image code  (https://www.youtube.com/watch?v=5WGb3DcpJhM&t=61s)
="<table><img src=""E:\paty\check\"&C2&"iso1.jpg""width=""140""height=""120""></table>"

c2 is component id colum
E:\paty\check is image folder path

# Tcl tk code


*createmarkpanel components 1 
 
set componentlist [hm_getmark comps 1]

*createmark assemblies 1
*createmark multibodies 1
*assemblymodifyhierarchy "image_done" 1 11

*clearmark comps 1


foreach compo $componentlist {

*createmark components 1 "byid" $compo
set compid [hm_getmark comps 1]
*isolateonlyentitybymark 1
*window_entitymark comps 1
*clearmark comps 1



set viewlist "iso1 iso2 top bottom leftside rightside rear front"

 foreach vwname $viewlist {



     *view "$vwname"

     *jpegfilenamed $compid$vwname.jpg
}
}
