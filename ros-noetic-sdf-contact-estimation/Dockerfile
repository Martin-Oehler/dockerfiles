FROM noetic-hector

# Clone repository
WORKDIR /home/hector/catkin_ws/src
ADD https://api.github.com/repos/tu-darmstadt-ros-pkg/sdf_contact_estimation/git/refs/heads/main sdf_contact_estimation_version.json
RUN git clone https://github.com/tu-darmstadt-ros-pkg/sdf_contact_estimation.git -b main

# Install dependencies
WORKDIR /home/hector/catkin_ws/src/sdf_contact_estimation
RUN rosdep install --from-paths . --ignore-src -r -y
RUN wstool init ../..
RUN wstool merge sdf_contact_estimation_https.rosinstall
RUN wstool update

# Build
RUN catkin build sdf_contact_estimation_demo
RUN echo "source /home/hector/catkin_ws/devel/setup.bash" >> /home/hector/.bashrc
