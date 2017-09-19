# Alpine Linux ruby

FROM youske/alpine-stdmachine:base
MAINTAINER youske miyakoshi <youske@gmail.com>

LABEL com.stdmachine.description="alpine ruby image" \
      com.stdmachine.role="ruby image"

ENV RBENV_ROOT /opt/rbenv \
       RUBY_VERSION 2.0.1

RUN PACKAGE='git ruby ruby-bundler ruby-irb libstdc++ linux-headers libffi-dev' && \
    BUILDPACKAGE='build-base musl-dev ruby-dev ' && \
    apk add ${PACKAGE} --no-cache && apk add ${BUILDPACKAGE} --no-cache -t buildtool && \
    echo 'gem: --no-document' >> /etc/gemrc && \
    echo "gem: --user-install --no-document" >> ~/.gemrc && \
    echo 'eval "$(rbenv init -)"' >> /etc/profile.d/rbenv.sh

RUN git clone git://github.com/sstephenson/rbenv.git ${RBENV_ROOT}
#&& \
#    git clone  https://github.com/sstephenson/ruby-build.git ${RBENV_ROOT}/plugins/ruby-build && \
#    git clone git://github.com/jf/rbenv-gemset.git ${RBENV_ROOT}/plugins/rbenv-gemset && \
#    ${RBENV_ROOT}/plugins/ruby-build/install.sh
    #&& \
#RUN    rbenv install ${RUBY_VERSION} && rbenv global ${RUBY_VERSION} && \
#    apk del buildtool --no-cache && rm -rf /tmp/* /var/cache/apk/* /root/.wget-hsts
