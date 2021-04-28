# iCompare

## Aims:
There are 4-5 integrators that everyone uses in Solar System dynamics that have never been fully compared and tested:
* OpenOrb
* FindOrb
* OrbFit
* JPL Horizons
* ADAM

We’d like to create an automated piece of code that propagates asteroids using all these integrators, compares their outputs, and presents it in some visually understandable way (e.g., a colourcoded matrix w. the asteroid on the Y axis and the integrator on the X axis).

More documentation will appear relative to completion rate.

## Currently available integrators
* OpenOrb using pyoorb (python bindings of OpenOrb)
* OrbFit via a Python wrapper that calls the OrbFit command-line code

## Currently available functionality
* receive ephemerides comparison via great circle distance in the form of a table 
* provide any asteroid or list of asteroids and receive visual comparison

## Future functionality
* parallelizing of code for asteroid lists
* addition of FindOrb to integrator suite
* please submit requests via pull request

## Requirements
* installation of OpenOrb and OrbFit, see here for OpenOrb: https://github.com/oorb/oorb, and here for OrbFit: http://adams.dm.unipi.it/orbfit/

Waiting for build to start...
Picked Git content provider.
Cloning into '/tmp/repo2docker_ta2_s68'...
HEAD is now at c2e0dd7 cleaning notebooks, folders and files. Code moved into module form
Building conda environment for python=3.7Using PythonBuildPack builder
Building conda environment for python=3.7Building conda environment for python=3.7Step 1/47 : FROM buildpack-deps:bionic
 ---> 17c4791bcf21
Step 2/47 : ENV DEBIAN_FRONTEND=noninteractive
 ---> Using cache
 ---> d967626324ed
Step 3/47 : RUN apt-get -qq update &&     apt-get -qq install --yes --no-install-recommends locales > /dev/null &&     apt-get -qq purge &&     apt-get -qq clean &&     rm -rf /var/lib/apt/lists/*
 ---> Using cache
 ---> bf87ff2ec940
Step 4/47 : RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen &&     locale-gen
 ---> Using cache
 ---> a82791e24ce4
Step 5/47 : ENV LC_ALL en_US.UTF-8
 ---> Using cache
 ---> 2ac60b3b6303
Step 6/47 : ENV LANG en_US.UTF-8
 ---> Using cache
 ---> 0c29e24b33c3
Step 7/47 : ENV LANGUAGE en_US.UTF-8
 ---> Using cache
 ---> 62d5a9b3f0e6
Step 8/47 : ENV SHELL /bin/bash
 ---> Using cache
 ---> 762c3f7a7c15
Step 9/47 : ARG NB_USER
 ---> Using cache
 ---> 8dd3da84e71e
Step 10/47 : ARG NB_UID
 ---> Using cache
 ---> 9c65deab5a48
Step 11/47 : ENV USER ${NB_USER}
 ---> Using cache
 ---> 8099a8d98d21
Step 12/47 : ENV HOME /home/${NB_USER}
 ---> Using cache
 ---> c0ba3d7745eb
Step 13/47 : RUN groupadd         --gid ${NB_UID}         ${NB_USER} &&     useradd         --comment "Default user"         --create-home         --gid ${NB_UID}         --no-log-init         --shell /bin/bash         --uid ${NB_UID}         ${NB_USER}
 ---> Using cache
 ---> ab9b9ed6ed51
Step 14/47 : RUN wget --quiet -O - https://deb.nodesource.com/gpgkey/nodesource.gpg.key |  apt-key add - &&     DISTRO="bionic" &&     echo "deb https://deb.nodesource.com/node_14.x $DISTRO main" >> /etc/apt/sources.list.d/nodesource.list &&     echo "deb-src https://deb.nodesource.com/node_14.x $DISTRO main" >> /etc/apt/sources.list.d/nodesource.list
 ---> Using cache
 ---> c9275bcee990
Step 15/47 : RUN apt-get -qq update &&     apt-get -qq install --yes --no-install-recommends   less        nodejs        unzip        > /dev/null &&     apt-get -qq purge &&     apt-get -qq clean &&     rm -rf /var/lib/apt/lists/*
 ---> Using cache
 ---> d045735a63ed
Step 16/47 : EXPOSE 8888
 ---> Using cache
 ---> d27580b6139f
Step 17/47 : ENV APP_BASE /srv
 ---> Using cache
 ---> add3191c8850
Step 18/47 : ENV NPM_DIR ${APP_BASE}/npm
 ---> Using cache
 ---> 1a0a0c88edaa
Step 19/47 : ENV NPM_CONFIG_GLOBALCONFIG ${NPM_DIR}/npmrc
 ---> Using cache
 ---> 46933f0e12f8
Step 20/47 : ENV CONDA_DIR ${APP_BASE}/conda
 ---> Using cache
 ---> ca44d5ab0592
Step 21/47 : ENV NB_PYTHON_PREFIX ${CONDA_DIR}/envs/notebook
 ---> Using cache
 ---> 3aa2343eeea4
Step 22/47 : ENV KERNEL_PYTHON_PREFIX ${NB_PYTHON_PREFIX}
 ---> Using cache
 ---> 4b24aeb6df59
Step 23/47 : ENV PATH ${NB_PYTHON_PREFIX}/bin:${CONDA_DIR}/bin:${NPM_DIR}/bin:${PATH}
 ---> Using cache
 ---> d16ed2536191
Step 24/47 : COPY --chown=1000:1000 build_script_files/-2fusr-2flib-2fpython3-2e8-2fsite-2dpackages-2frepo2docker-2fbuildpacks-2fconda-2factivate-2dconda-2esh-391af5 /etc/profile.d/activate-conda.sh
 ---> Using cache
 ---> 2e278b05240a
Step 25/47 : COPY --chown=1000:1000 build_script_files/-2fusr-2flib-2fpython3-2e8-2fsite-2dpackages-2frepo2docker-2fbuildpacks-2fconda-2fenvironment-2epy-2d3-2e7-2efrozen-2eyml-037262 /tmp/environment.yml
 ---> Using cache
 ---> b058265dc099
Step 26/47 : COPY --chown=1000:1000 build_script_files/-2fusr-2flib-2fpython3-2e8-2fsite-2dpackages-2frepo2docker-2fbuildpacks-2fconda-2finstall-2dminiforge-2ebash-514214 /tmp/install-miniforge.bash
 ---> Using cache
 ---> 8fc33b05aebe
Step 27/47 : RUN mkdir -p ${NPM_DIR} && chown -R ${NB_USER}:${NB_USER} ${NPM_DIR}
 ---> Using cache
 ---> 6aca84291a66
Step 28/47 : USER ${NB_USER}
 ---> Using cache
 ---> 9c62b96ced8f
Step 29/47 : RUN npm config --global set prefix ${NPM_DIR}
 ---> Using cache
 ---> 74879b96fe75
Step 30/47 : USER root
 ---> Using cache
 ---> 8c25495f2faa
Step 31/47 : RUN TIMEFORMAT='time: %3R' bash -c 'time /tmp/install-miniforge.bash' && rm /tmp/install-miniforge.bash /tmp/environment.yml
 ---> Using cache
 ---> 488bce192592
Step 32/47 : ARG REPO_DIR=${HOME}
 ---> Using cache
 ---> 4839e040f3f4
Step 33/47 : ENV REPO_DIR ${REPO_DIR}
 ---> Using cache
 ---> cbc2d7bd53ca
Step 34/47 : WORKDIR ${REPO_DIR}
 ---> Using cache
 ---> 76ef8ef61b29
Step 35/47 : RUN chown ${NB_USER}:${NB_USER} ${REPO_DIR}
 ---> Using cache
 ---> ef22c5fc9df9
Step 36/47 : ENV PATH ${HOME}/.local/bin:${REPO_DIR}/.local/bin:${PATH}
 ---> Using cache
 ---> 2bfaf872d1c6
Step 37/47 : ENV CONDA_DEFAULT_ENV ${KERNEL_PYTHON_PREFIX}
 ---> Using cache
 ---> e2727ff377b7
Step 38/47 : COPY --chown=1000:1000 src/ ${REPO_DIR}
 ---> c2ec27d8955d
Step 39/47 : LABEL repo2docker.ref="c2e0dd7a14e48a7fd6e444221d5066a24bac59bb"
 ---> [Warning] Your kernel does not support swap limit capabilities or the cgroup is not mounted. Memory limited without swap.
 ---> Running in 9bfbb0006433
Removing intermediate container 9bfbb0006433
 ---> 8499d25841eb
Step 40/47 : LABEL repo2docker.repo="https://github.com/maria8ch/iCompare"
 ---> [Warning] Your kernel does not support swap limit capabilities or the cgroup is not mounted. Memory limited without swap.
 ---> Running in 811969e78eac
Removing intermediate container 811969e78eac
 ---> 2869ca0a7ffb
Step 41/47 : LABEL repo2docker.version="2021.03.0+15.g73ab48a"
 ---> [Warning] Your kernel does not support swap limit capabilities or the cgroup is not mounted. Memory limited without swap.
 ---> Running in 6f34e483e522
Removing intermediate container 6f34e483e522
 ---> 9ba6a25f5b82
Step 42/47 : USER ${NB_USER}
 ---> [Warning] Your kernel does not support swap limit capabilities or the cgroup is not mounted. Memory limited without swap.
 ---> Running in 405cc9df69b2
Removing intermediate container 405cc9df69b2
 ---> b018042f55e6
Step 43/47 : ENV PYTHONUNBUFFERED=1
 ---> [Warning] Your kernel does not support swap limit capabilities or the cgroup is not mounted. Memory limited without swap.
 ---> Running in 9fc34eb3901f
Removing intermediate container 9fc34eb3901f
 ---> 296519e63db4
Step 44/47 : COPY /python3-login /usr/local/bin/python3-login
 ---> 8aa1e7542087
Step 45/47 : COPY /repo2docker-entrypoint /usr/local/bin/repo2docker-entrypoint
 ---> fa3b678728d9
Step 46/47 : ENTRYPOINT ["/usr/local/bin/repo2docker-entrypoint"]
 ---> [Warning] Your kernel does not support swap limit capabilities or the cgroup is not mounted. Memory limited without swap.
 ---> Running in 273949b47d0b
Removing intermediate container 273949b47d0b
 ---> 19578bdc0ca4
Step 47/47 : CMD ["jupyter", "notebook", "--ip", "0.0.0.0"]
 ---> [Warning] Your kernel does not support swap limit capabilities or the cgroup is not mounted. Memory limited without swap.
 ---> Running in 7c85aa96b8e9
Removing intermediate container 7c85aa96b8e9
 ---> 4e344b832213
{"aux": {"ID": "sha256:4e344b83221301aba988cf8ceb96c6c1b4d9618b91669d6761bc5a6b2729027b"}}Successfully built 4e344b832213
Successfully tagged turingmybinder/binder-prod-maria8ch-2dicompare-c9b142:c2e0dd7a14e48a7fd6e444221d5066a24bac59bb
Pushing image
Pushing image
Pushing image
Pushing image
Pushing image
Pushing image
Successfully pushed turingmybinder/binder-prod-maria8ch-2dicompare-c9b142:c2e0dd7a14e48a7fd6e444221d5066a24bac59bb
