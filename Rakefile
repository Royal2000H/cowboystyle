namespace :deploy do
  task :night do
    cmd = %w(REDDIT_STYLESHEET_MODE=night
             REDDIT_STYLESHEET_COMPILE=false ) << 
             "REDDIT_SUBREDDIT=" + ENV['REDDIT_SUBREDDIT_DEV_NIGHT'] <<
             "rake deploy:deploy"
    cmd = cmd.reverse.join(" ")
    sh cmd
  end

  task :day do
    cmd = %w(REDDIT_STYLESHEET_MODE=day
             REDDIT_STYLESHEET_COMPILE=false ) << 
             "REDDIT_SUBREDDIT=" + ENV['REDDIT_SUBREDDIT_DEV_DAY'] <<
             "rake deploy:deploy"
    cmd = cmd.reverse.join(" ")
    sh cmd
  end

  task :temporal do
    cmd = %w(REDDIT_STYLESHEET_MODE=auto
             REDDIT_STYLESHEET_COMPILE=false ) << 
             "REDDIT_SUBREDDIT=" + ENV['REDDIT_SUBREDDIT_DEV_TEMPORAL'] <<
             "rake deploy:deploy"
    cmd = cmd.reverse.join(" ")
    sh cmd
  end

  multitask :all => [:temporal, :day, :night]

  task :deploy do
    sh "python deploy.py"
  end
end

task :compass do
  sh("compass compile")  
end

task :clipboard_day do
  sh("cat stylesheets/day.css | pbcopy")
end

task :clipboard_night do
  sh("cat stylesheets/night.css | pbcopy")
end
