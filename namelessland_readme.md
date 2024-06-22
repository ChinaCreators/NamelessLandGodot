# build command
```powershell
scons p=windows vsproj=yes dev_build=yes module_mono_enabled=yes precision=double
# now use vs to compile the engine
bin/godot.windows.editor.dev.x86_64.mono --headless --generate-mono-glue modules/mono/glue
# my_local_source is your local nuget source path, make sure is use \ instead of /
dotnet nuget add source <my_local_source> --name MyLocalNugetSource
python ./modules/mono/build_scripts/build_assemblies.py --godot-output-dir ./bin --push-nupkgs-local <my_local_source> --precision=double
```
