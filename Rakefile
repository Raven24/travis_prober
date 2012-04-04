
task :check_versions do
  puts "## Check program versions"
  ["firefox", "mysql", "psql", "ruby", "gem", "bundle", "Xvfb"].each do |bin|
    puts "  # Testing #{bin}"
    begin
      version = `#{bin} --version`.sub(/\n(.+)/, ", \1")
    rescue
      version = `apt-show-versions #{bin.downcase}`
    end
    puts "  -- version: #{version}"
    puts "  -- path:    " + `which #{bin}`
    puts ""
  end
end

task :list_processes do
  puts "## Listing processes"
  puts `ps ux`
end

task :travis => [:check_versions, :list_processes] do
  puts "## Done"
end
