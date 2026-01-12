# Installation

By default, on UNIX-based OS's matplotlib looks for user-defined stylessheets in `~/.config/matplotlib/stylelib`. 

On Windows, I don't know where it looks but you can check where matplotlib is searching by using their Python API to query paths:
```
import matplotlib as mpl
import matplotlib.style.core as msc

print("Config dir:")
print(mpl.get_configdir())

print("\nData dir:")
print(mpl.get_data_path())

print("\nStyle search paths:") 
for p in msc.USER_LIBRARY_PATHS:
    print(p)
print(msc.BASE_LIBRARY_PATH)

> Config dir:
> /home/ray/.config/matplotlib
>
> Data dir:
> /home/ray/.cache/uv/builds-v0/.tmpmiFQo2/lib/python3.12/site-packages/matplotlib/mpl-data
> 
> Style search paths:
> /home/ray/.config/matplotlib/stylelib <-- global config, independent of your particular venv
> /home/ray/.cache/uv/builds-v0/.tmpmiFQo2/lib/python3.12/site-packages/matplotlib/mpl-data/stylelib <-- this is local to a UV virtual environment
```

On Linux you can simply use the following command.
```
mkdir -p ~/.config/matplotlib/stylelib && 
wget -O ~/.config/matplotlib/stylelib/ray.mplstyle \
  https://raw.githubusercontent.com/rayhagimoto/mplstyle/refs/heads/main/ray.mplstyle
```
