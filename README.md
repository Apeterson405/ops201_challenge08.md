# ops201_challenge08.md


@echo off
setlocal

REM Prompt user for source folder path
set /p source_path="Enter the source folder path: "
REM Prompt user for destination folder path
set /p dest_path="Enter the destination folder path: "

REM Validate source folder path
if not exist "%source_path%" (
    echo Source folder path is invalid or does not exist.
    pause
    exit /b 1
)

REM Validate destination folder path
if not exist "%dest_path%" (
    echo Destination folder path is invalid or does not exist.
    pause
    exit /b 1
)

REM Perform copy operation using ROBOCOPY
echo Copying files from %source_path% to %dest_path% ...
robocopy "%source_path%" "%dest_path%" /e /v /tee /np

echo.
echo Copy operation completed.

:end
pause
