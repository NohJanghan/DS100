Public-facing repo for materials used in the Summer 2025 iteration of Data 100 at UC Berkeley.

### Installation Guide for Otto
In Mac, to make PDFs, you should install `pandoc` and `basictex`.
```bash
$ brew install pandoc
$ brew install basictex
```
Also, you should install following packages:
```bash
$ sudo tlmgr install enumitem soul
```

For excluding outputs and metadata of `.ipynb` files,you should add the following to your git config.
```
[filter "strip-notebook-output"]
	clean = "jupyter nbconvert --ClearOutputPreprocessor.enabled=True --ClearMetadataPreprocessor.enabled=True --to=notebook --stdin --stdout --log-level=ERROR"
```
If your environment doesn't have a default python env containing `jupyter nbconvert`, refer to [this](https://stackoverflow.com/a/73218382).  
If you use `uv` or `venv`, you can use the following snippet for your config.
```
[filter "strip-notebook-output"]
	clean = "\"[YOUR PROJECT]/.venv/bin/jupyter-nbconvert\" --ClearOutputPreprocessor.enabled=True --ClearMetadataPreprocessor.enabled=False --to=notebook --stdin --stdout --log-level=ERROR"
```