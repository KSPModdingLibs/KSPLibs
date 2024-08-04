This repository contains KSP and Unity DLLs that have been stripped of their method bodies.  They contain type and method information only, so that mods can compile against them.

Note that these are NOT publicized (all fields/methods changed to public) because that can cause compile errors when overrideing protected methods.
If you need to use a publicizer, just use one that works with the msbuild process - those should still work with these stripped libraries.  Suggestions:

* [Krafs](https://github.com/krafs/Publicizer)
* [BepInEx](https://github.com/BepInEx/BepInEx.AssemblyPublicizer)

# Methodology

1. Install the [BepInEx publicizer](https://github.com/BepInEx/BepInEx.AssemblyPublicizer):  
   `dotnet tool install -g BepInEx.AssemblyPublicizer.Cli`
2. Make a copy of KSP_x64_Data/Managed and open it in a command console
3. Run `assembly-publicizer *.dll -f --strip-only`
4. Create a zip file with the results, preserving the directory structure relative to the KSP root.  
   That is, the zip file should contain KSP_x64_Data as the top-level item.
