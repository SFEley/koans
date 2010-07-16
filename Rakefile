require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "koans"
    gem.summary = %Q{Ruby Koans for Ruby 1.9 and RSpec 2}
    gem.description = %Q{This gem is an idea-lift from Jim Weirich's Ruby Koans (http://github.com/edgecase/ruby_koans), a brilliant set of TDD exercises intended to teach the Ruby language. Each koan is a failing unit test; the student modifies the code to make the test pass, and learns a little more about Ruby each time. The original koans were written for Ruby 1.8.x and Test::Unit. These koans are written for 1.9.2 and use the BDD style of RSpec, which the author believes to be more expressive and instructive. Bootstrapping has also been refined, to make it easier for the true novice to get started. (Simply 'gem install koans' and then type 'koans' at the command line.)}
    gem.email = "sfeley@gmail.com"
    gem.homepage = "http://github.com/SFEley/koans"
    gem.authors = ["Stephen Eley"]
    gem.add_development_dependency "rspec", ">= 1.2.9"
    gem.add_development_dependency "yard", ">= 0"
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :spec => :check_dependencies

task :default => :spec

begin
  require 'yard'
  YARD::Rake::YardocTask.new
rescue LoadError
  task :yardoc do
    abort "YARD is not available. In order to run yardoc, you must: sudo gem install yard"
  end
end
