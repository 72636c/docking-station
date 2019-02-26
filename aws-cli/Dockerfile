FROM python:3.7-alpine

RUN pip3 install --upgrade 'awscli>=1.16,<1.17'

RUN export PATH="${PATH}:'$(pip3 show awscli)'"

ENTRYPOINT ["aws"]
CMD ["--help"]
