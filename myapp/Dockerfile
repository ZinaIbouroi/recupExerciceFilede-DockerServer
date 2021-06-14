FROM ruby 
COPY myapp.rb /myapp/
RUN  cd myapp/ 
RUN  gem install sinatra
RUN  gem install puma
CMD  ruby /myapp/myapp.rb -o 0.0.0.0
