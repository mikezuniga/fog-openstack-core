require "bundler/gem_tasks"
require 'rake/testtask'

Rake::TestTask.new do |t|
  t.libs.push 'spec'
  t.pattern = 'spec/**/*_spec.rb'
  t.warning = true
  t.verbose = true
end

task(default: :test)

desc 'Generates a coverage report'
task :coverage do
  ENV['COVERAGE'] = 'true'
  Rake::Task['test'].execute
end

desc 'Reset Request Cassettes'
namespace :vcr do
  task :reset do
    `rm -fr spec/cassettes/*`
  end
end
