# Carpeta_segura
Carpeta con clave en el escritorio
	
cls
@ECHO OFF
title Folder CarpetaProtegida
if EXIST "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" goto UNLOCK
if NOT EXIST CarpetaProtegida goto MDLOCKER
:CONFIRM
echo Quiere ocultar la CarpetaProtegida? (S/N)
set/p "cho="
if %cho%==S goto LOCK
if %cho%==s goto LOCK
if %cho%==n goto END
if %cho%==N goto END
echo Invalid choice.
goto CONFIRM
:LOCK
ren CarpetaProtegida "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
attrib +h +s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
echo Folder locked
goto End
:UNLOCK
echo Dime las palabras magicas
set/p "pass="
if NOT %pass%== CAMBIE-ESTE-TEXTO-POR-SU-CONTRASEÑA goto FAIL
attrib -h -s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
ren "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" CarpetaProtegida
echo Folder Unlocked successfully
goto End
AIL
echo Invalid password
goto end
:MDLOCKER
md CarpetaProtegida
echo CarpetaProtegida created successfully
goto End
:End
-------Guardalo con.bat------
