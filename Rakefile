require 'pony'

task :default => :run

desc 'Run app'
task :run do 
  system "rackup -s thin"
end

desc 'Maintain galleries'
task :cron do
  puts "Building galleries. #{Time.now.strftime('%Y/%m/%d %H:%M:%S')}"
  
  
  
  Pony.mail :to             => 'pieter@wellconsidered.be',
            :from           => 'pieter@wellconsidered.be',
            :subject        => 'Cron executed!', 
            :via            => :smtp, 
            :via_options    => {:address                => 'smtp.gmail.com',
                                :port                   => '587',
                                :enable_starttls_auto   => true,
                                :user_name              => ENV['GMAIL_USER'],
                                :password               => ENV['GMAIL_PASSWORD'],
                                :authentication         => :plain,
                                :domain                 => "wellconsidered.be"
                               }
end