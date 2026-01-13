FROM zivgitlab.wwu.io/pymor/pymor/ci-current:ae1cdaeb538f2067977054345828024b730a4a372e1af766c504f5015aa763eb

# binder wants to set the NB_ vars anyways, so we use it to service both setups
ARG NB_USER
ARG NB_UID

USER root
RUN rm -rf /pymor && useradd -d /pymor --shell /bin/bash -u ${NB_UID} -o -c "" -m ${NB_USER}
RUN pip install git+https://github.com/pymor/pymor@6206db257de973f88caf65cb728159c9a29b5e6e

ENV USER=${NB_USER} \
    HOME=/pymor

RUN cd /pymor && wget  https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/218cda5bb1e3c69656498232df908d06/tutorial_unstable_lti_systems.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/e83e03d63417bf02b638d5214e9dc015/getting_started.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/36d790e69b87fb8012d42aadb38afd2c/tutorial_external_solver.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/e186cc59e1a399f6fe70c42f528ffc71/tutorial_ph.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/1f641b2cd53373bc47fc16373ad56a4f/tutorial_interact.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/9457b171c152971cf5260fa1be5262db/tutorial_lti_systems.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/76690833ecbd86286328712e1ba67763/mor_methods.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/711687a99e3da3e3418d3972ceb042e5/tutorial_builtin_discretizer.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/1a27ade3bd8436eee3f8b145a3a5890b/tutorial_basis_generation.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/8f161ce351cc8d219b0f29da1829f025/tutorial_mor_with_ml.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/d4fa2c323a66d86c0ebbe8f8d289ba23/tutorial_interpolation.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/049752ef291d62bd7bcde4a95068666e/tutorial_bt.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/1000b3f568829899be8a4f7a0b7f7e9a/tutorial_optimization.ipynb https://docs.pymor.org/bump-version-to-2026-1-dev0/_downloads/242c69f4d668a8e7d0652f1c7a06f83b/tutorial_projection.ipynb
RUN chown -R ${NB_USER} /pymor
USER ${NB_USER}

ENTRYPOINT []
WORKDIR /pymor
