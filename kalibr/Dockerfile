FROM xqms/kalibr:latest
SHELL ["/bin/bash", "-c"]
RUN source /workspace/devel/setup.bash && roscd kalibr && git remote add tuda https://github.com/tu-darmstadt-ros-pkg/kalibr.git && git fetch tuda && git checkout rgba8_support
RUN echo "source /workspace/devel/setup.bash" >> /root/.bashrc
RUN sudo apt update
RUN sudo apt install -y libcairo2-dev
RUN sudo apt install -y python-pip
RUN pip2 install pycairo
WORKDIR /mnt
ENTRYPOINT echo "Start calibration with kalibr_calibrate_cameras" && /bin/bash
