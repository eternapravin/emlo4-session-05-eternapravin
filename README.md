# Lightning Hydra Template

## UV

```bash
UV_EXTRA_INDEX_URL=https://download.pytorch.org/whl/cpu uv sync
```

```bash
export UV_EXTRA_INDEX_URL=https://download.pytorch.org/whl/cpu
```

## Train

Dev Run

```bash
python src/train.py experiment=catdog_ex +trainer.fast_dev_run=True
```

```bash
python src/train.py experiment=catdog_ex +trainer.log_every_n_steps=5
```

multi run

```bash
python src/train.py --multirun experiment=catdog_ex model.embed_dim=16,32,64 +trainer.log_every_n_steps=5
```

optuna

```bash
python src/train.py --multirun hparam=catdog_vit_hparam +trainer.log_every_n_steps=5 hydra.sweeper.n_jobs=4
```

## Docker

```bash
docker build -t lightning-hydra .
```

```bash
docker run -it --rm \
	-v `pwd`/data:/app/data \
	-v `pwd`/logs:/app/logs \
	lightning-hydra \
	python src/train.py experiment=catdog_ex
```

## Coverage

```bash
coverage run -m pytest
coverage report -m
```

## Github Actions

Test locally with https://nektosact.com/
