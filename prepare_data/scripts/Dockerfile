FROM armswdev/tensorflow-arm-neoverse:latest

COPY requirements.txt ./
#RUN apt-get update
#RUN apt-get install ffmpeg libsm6 libxext6  -y
RUN pip install --no-cache-dir -r requirements.txt

ADD retrieve_and_prepare.py /usr/local/bin/retrieve_and_prepare.py
ADD eff100-rgb.h5 /models/eff100-rgb.h5

# because of segmentation fault
ENV TF_ENABLE_ONEDNN_OPTS=0

CMD [ "python", "/usr/local/bin/retrieve_and_prepare.py" ]