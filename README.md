




[![Multi-Modality](agorabanner.png)](https://discord.com/servers/agora-999382051935506503)
# AI-Intrusion-Detection-System
**Group 3**

[![Join our Discord](https://img.shields.io/badge/Discord-Join%20our%20server-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/agora-999382051935506503) [![Subscribe on YouTube](https://img.shields.io/badge/YouTube-Subscribe-red?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@kyegomez3242) [![Connect on LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kye-g-38759a207/) [![Follow on X.com](https://img.shields.io/badge/X.com-Follow-1DA1F2?style=for-the-badge&logo=x&logoColor=white)](https://x.com/kyegomezb)

A easy, reliable, fluid template for python packages complete with docs, testing suites, readme's, github workflows, linting and much much more


## Prerequisite

The environment needed to set up based on conda

```bash
conda create -n IDS_env python=3.10
conda activate IDS_env
pip install flask scikit-learn pandas scapy numpy joblib 
```

Download (click icon) Npcap to adapt *scapy* on windows (no need for linux)

[![Multi-Modality](https://npcap.com/images/sitelogo-2x.png)]((https://npcap.com/dist/npcap-1.85.exe))

# Quick Run
Initially run the starter (web server) file

```python
python app.py
```
You'll get something like this:

```output
[Collector] Sniffer started
 * Serving Flask app 'app'
 * Debug mode: on
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:5000
 * Running on http://26.26.26.1:5000
Press CTRL+C to quit
 * Restarting with stat
[Collector] Sniffer started
 * Debugger is active!
 * Debugger PIN: 274-065-662
```

Then randomly choose one of the two websites to enter.



### Code Quality 🧹

- `make style` to format the code
- `make check_code_quality` to check code quality (PEP8 basically)
- `black .`
- `ruff . --fix`

### Tests 🧪

[`pytests`](https://docs.pytest.org/en/7.1.x/) is used to run our tests.

### Publish on PyPi 🚀

**Important**: Before publishing, edit `__version__` in [src/__init__](/src/__init__.py) to match the wanted new version.

```
poetry build
poetry publish
```

### CI/CD 🤖

We use [GitHub actions](https://github.com/features/actions) to automatically run tests and check code quality when a new PR is done on `main`.

On any pull request, we will check the code quality and tests.

When a new release is created, we will try to push the new code to PyPi. We use [`twine`](https://twine.readthedocs.io/en/stable/) to make our life easier. 

The **correct steps** to create a new realease are the following:
- edit `__version__` in [src/__init__](/src/__init__.py) to match the wanted new version.
- create a new [`tag`](https://git-scm.com/docs/git-tag) with the release name, e.g. `git tag v0.0.1 && git push origin v0.0.1` or from the GitHub UI.
- create a new release from GitHub UI

The CI will run when you create the new release.

