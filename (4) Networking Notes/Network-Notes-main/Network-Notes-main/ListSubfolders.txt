@echo off
setlocal enabledelayedexpansion

:: Prompt the user for a directory
set /p directory=Enter the path of the folder: 

:: Check if the directory exists
if not exist "%directory%" (
    echo The folder "%directory%" does not exist.
    exit /b
)

:: List all subfolders
echo Listing subfolders in: %directory%
echo.
for /d %%F in ("%directory%\*") do (
    echo %%F
)

pause
