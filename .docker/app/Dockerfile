FROM jruby:9

# 基本的なパッケージのインストール
RUN apt-get update -qq \
 && apt-get install -y --no-install-recommends \
      build-essential \
      curl \
      gnupg gnupg1 gnupg2 \
      default-libmysqlclient-dev \
      vim \
      less

# Node.js と Yarn をインストールして不要なファイルを autoremove / clean で削除
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
 && curl -sSL https://deb.nodesource.com/setup_10.x | bash - \
 && echo deb https://dl.yarnpkg.com/debian/ stable main | tee /etc/apt/sources.list.d/yarn.list \
 && apt-get install -y --no-install-recommends yarn nodejs \
 && apt-get autoremove -y \
 && apt-get clean
