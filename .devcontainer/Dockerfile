FROM ubuntu

RUN apt update
RUN DEBIAN_FRONTEND=noninteractive apt install --no-install-recommends -y \
        python3 python3-pip git curl locales \
        texlive texlive-extra-utils \
        texlive-base texlive-latex-recommended texlive-latex-extra \
        latexmk texlive-xetex texlive-pstricks texlive-science \
        texlive-fonts-recommended texlive-fonts-extra \
        texlive-lang-german texlive-lang-english\
        texlive-bibtex-extra biber 

        
# generating locales
RUN sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=en_US.UTF-8
ENV LANGUAGE=en_US.UTF-8 LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8

# Keeps Python from generating .pyc files in the container
ENV PYTHONDONTWRITEBYTECODE=1
# Turns off buffering for easier container logging
ENV PYTHONUNBUFFERED=1
RUN pip3 install pygments
RUN rm -rf /var/cache/apt/*

RUN mkdir /tex
# WORKDIR /tex
