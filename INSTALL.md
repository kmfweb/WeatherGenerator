```
# Make sure you have a recent version of gcc in your environment:
gcc -version
# If too old, e.g., <9:
module avail gg, module load gcc/12.2.0

# Make sure your python includes cpython (if you do not use uv's python)
python -c "import sys; print(sys.implementation.name)"
# Must print cpython, then OK

# install uv 
# Suggested solution for HPC systems:
%>curl -LsSf https://astral.sh/uv/0.6.5/install.sh | sh
# Make it permanent:
export PATH="$HOME/.cargo/bin:$PATH"
echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
# Check if OK: uv --version
 
# git clone / fork WeatherGenerator repo
%>cd WeatherGenerator
%>uv sync
 
 
%>uv run train
```
