FROM centos:7.5.1804
MAINTAINER ligl
RUN yum -y install epel-release wget && \
	rpm --import http://li.nux.ro/download/nux/RPM-GPG-KEY-nux.ro && \
	rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm && \
	yum -y install ffmpeg ffmpeg-devel && \
	mkdir -p /phenix/RPMS /phenix/source && \
	wget -O /phenix/RPMS/LibreOffice_6.2.2_Linux_x86-64_rpm.tar.gz http://mirrors.ustc.edu.cn/tdf/libreoffice/stable/6.2.2/rpm/x86_64/LibreOffice_6.2.2_Linux_x86-64_rpm.tar.gz && \
	wget -O /phenix/RPMS/LibreOffice_6.2.2_Linux_x86-64_rpm_sdk.tar.gz http://mirrors.ustc.edu.cn/tdf/libreoffice/stable/6.2.2/rpm/x86_64/LibreOffice_6.2.2_Linux_x86-64_rpm_sdk.tar.gz && \
	wget -O /phenix/RPMS/LibreOffice_6.2.2_Linux_x86-64_rpm_langpack_zh-CN.tar.gz http://mirrors.ustc.edu.cn/tdf/libreoffice/stable/6.2.2/rpm/x86_64/LibreOffice_6.2.2_Linux_x86-64_rpm_langpack_zh-CN.tar.gz
WORKDIR /phenix
ADD phenix.tar.gz /phenix/
RUN tar -xzf /phenix/RPMS/LibreOffice_6.2.2_Linux_x86-64_rpm.tar.gz -C /phenix/RPMS/ && \
		tar -xzf /phenix/RPMS/LibreOffice_6.2.2_Linux_x86-64_rpm_sdk.tar.gz -C /phenix/RPMS/ && \
		tar -xzf /phenix/RPMS/LibreOffice_6.2.2_Linux_x86-64_rpm_langpack_zh-CN.tar.gz -C /phenix/RPMS/ && \
		cd /phenix/RPMS/LibreOffice_6.2.2.2_Linux_x86-64_rpm/RPMS && yum -y localinstall *.rpm && \
		cd /phenix/RPMS/LibreOffice_6.2.2.2_Linux_x86-64_rpm_langpack_zh-CN/ && yum -y localinstall *.rpm && \
		chmod +x /phenix/cmd/phenix
EXPOSE 2228
ADD run.sh /
RUN chmod +x /run.sh && rm -rf /phenix/RPMS
ENTRYPOINT ["bash","-c","/run.sh"]
