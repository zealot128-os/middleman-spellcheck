require "bundler/gem_tasks"
Bundler::GemHelper.install_tasks

require 'cucumber/rake/task'

Cucumber::Rake::Task.new(:cucumber, 'Run features that should pass') do |t|
  exempt_tags = ""
  exempt_tags << "--tags ~@nojava " if RUBY_PLATFORM == "java"
  t.cucumber_opts = "--color --tags ~@wip #{exempt_tags} --strict --format #{ENV['CUCUMBER_FORMAT'] || 'pretty'}"
end

task :test => ["cucumber"]
task :default => :test
