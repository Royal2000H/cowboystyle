# A sample Guardfile
# More info at https://github.com/guard/guard#readme

guard 'compass' do
  watch(/^sass\/(.*)\.s[ac]ss/)
end

# Add files and commands to this file, like the example:
#   watch(%r{file/path}) { `command(s)` }
#
guard 'shell' do
    watch(%r{stylesheets/day\.css}) {
            `rake deploy:day`
        }
    watch(%r{stylesheets/night\.css}) {
            `rake deploy:night`
        }
    watch(%r{templates/sidebar\.md}) {
            `rake deploy:test`
        }
end

