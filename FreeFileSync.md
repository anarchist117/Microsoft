# FreeFileSync
1. Create task in FreeFileSyn
2. Save as batch job "BatchRun.ffs_batch"
  ```
  C:\Program Files\FreeFileSync\BatchRun.ffs_batch
  ```
3. Close FreeFileSyn

# RealTimeSync
4. Create task in RealTimeSync
5. Select "Folder to watch for changes"
6. Command line:
  ```
  "C:\Program Files\FreeFileSync\FreeFileSync.exe" "C:\Program Files\FreeFileSync\BatchRun.ffs_batch"
  ```
7. Save as RealTime.ffs_real
8. Create a shortcut and add to Startup (shell:startup)
