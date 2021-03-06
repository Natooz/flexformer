# Flexformer

[![PyPI version fury.io](https://badge.fury.io/py/flexformer.svg)](https://pypi.python.org/pypi/flexformer/)

Hi 👋, this is my PyTorch implementation of the **Transformer** architecture. I use it as a flexible framework to build custom architectures and play around with attention for my projects. It includes several positional encodings, some optimizations from recent research, and also [utilities](flexformer/utils.py), [metrics](flexformer/metrics.py) and [sampling](flexformer/sampling.py) functions.

Feel free to use it, take the code for your projects, and raise an issue if you have question or a pull request if you want to contribute.

```shell
pip install flexformer
```

Simplest example:

```python
from flexformer import Transformer
from torch import randint

model = Transformer(num_encoder_layers=8, num_decoder_layers=8, d_model=512, nhead=8, dim_feedforward=2048, dropout=0.2,
                    num_classes=5000, padding_token=0)

x = randint(low=0, high=5000, size=(400, 16))
y = model(x, auto_padding_mask=True)
```

I built it for my own usage, so you won't find documentation besides the docstring.

### Flexformer implements:

* Linear attention, with [Elu](https://arxiv.org/abs/2006.16236) and [Favor+](https://arxiv.org/abs/2009.14794) feature maps
* [Rotary](https://arxiv.org/abs/2104.09864) and [relative](https://arxiv.org/abs/1809.04281) positional encodings (rotary used by default)

### Disclaimer

I might release updates without stating changelogs, so if anything breaks don't hesitate to check the commits or raise an issue.
