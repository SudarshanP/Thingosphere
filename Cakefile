{exec} = require 'child_process'

task 'localg', 'This launches gae dev server', ->
  console.log 'Starting App Engine Server on Localhost:'
  child = exec 'python ~/gae/dev_appserver.py server'
  child.stdout.on 'data', (data) -> console.log data
  child.stderr.on 'data', (data) -> console.log data

task 'localb', 'This launches brunch dev server', ->
  console.log 'Starting Brunch Server on Localhost:'
  child = exec 'cd client ; brunch watch --server'
  child.stdout.on 'data', (data) -> console.log data
  child.stderr.on 'data', (data) -> console.log data

task 'build', 'Builds client and stores output in brunch folder of server', ->
  console.log 'Building Client:'
  child = exec 'cd client ; brunch build -o ../server/brunch'
  child.stdout.on 'data', (data) -> console.log data
  child.stderr.on 'data', (data) -> console.log data
    
task 'deploy', 'This deploys to Appengine', ->
  console.log 'Deploying to Appengine!'
  child = exec 'python ~/gae/appcfg.py update server'
  child.stdout.on 'data', (data) -> console.log data
  child.stderr.on 'data', (data) -> console.log data
