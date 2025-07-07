# Colletion of onliners

## Rename "_" into " " (or vice versa)
for file in 20210117_1403*;do mv -b -v "$file" "${file//"_"/" "}";done
## Renaming Videos
for file in 202107* ;do mv -b -v "$file" "${file//\!/""}";done
for file in 202104* ;do mv -b -v "$file" "${file//"_Altersfreigabe_ ab 6"/""}";done
for file in 20* ;do mv -b -v "$file" "${file//"_Doku-Reihe"/" "}";done 
## Renaming when filename is too long
for file in 20* ;do mv -b -v "$file" "file=${file::99} ";done
