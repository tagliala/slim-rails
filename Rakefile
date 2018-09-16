#!/usr/bin/env rake
require 'bundler'
Bundler::GemHelper.install_tasks

require 'rubocop/rake_task'
RuboCop::RakeTask.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/*_test.rb'
  test.verbose = true
end

task(:test).prerequisites.unshift task(:rubocop)

task default: :test
