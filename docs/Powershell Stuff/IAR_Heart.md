# IAR Heartbeat
This Script tests to see if IAR is running and if not it will log it and restart it. 

``` powershell
$Source = "E:\Recordings\TwoToneDetect73f\logfiles\heartbeat.log"
$application = "E:\Recordings\TwoToneDetect73f\TwoToneDetect73f.exe"
$LogFile = "E:\Recordings\TwoToneDetect73f\logfiles\crashes.txt"
$File = Get-ItemProperty -Path $source -Name LastWriteTime
$Date = Get-Date -Format "MM/dd/yyyy HH:mm:ss"
$Crashed1 = $date + " - Applcation wasn't running and we restarted it"
$Crashed2 = $date + " - Applcation was running but stalled and we restarted it"

$Currenttime =  (Get-date).Addminutes(-2)
If ($file.LastWriteTime -gt $Currenttime ){
    write-host "Application is all fine"
}else{
    write-host "Application isn't fine"
    $Two = Get-process -name "TwoToneDetect73f" -ErrorAction SilentlyContinue
    if ($two -eq $null){
        write-host "Two Tone Detect isn't running...."
        write-host "Starting Two Tone Detect"
        Start-Process -FilePath $application
        Add-Content -Path $LogFile -Value $Crashed1 -PassThru
    }else{
        write-host "Two Tone Detect is running...."
        write-host "Stopping Two Tone Detect...."
        $two | stop-service
        write-host "Starting Two Tone Detect"
        Start-Process -FilePath $application
        Add-Content -Path $LogFile -Value $Crashed2 -PassThru
    }
}


```