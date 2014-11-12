rhq_nodb
========

RHQ (without DB) contianer repository

Demo how RHQ Dockerfile works https://plus.google.com/u/0/events/clp274bhmdfvi4ol7csh2fd7n38?authkey=CPGuh8eZtrG5oAE

To build and run rhq docker container:

1. Install docker-io $ yum -y install docker-io 
2. Build rhq image from Dockerfile $ ./build.sh 
3. Run rhq image $ ./run.sh
4. Clean up running rhq container $  ./run.sh cleanup
5. Delete old/current rhq image $ ./run.sh purge

rhq should be linked to postgresql container 

# Launch Postgresql db
$ docker run -d --name rhq-psql vnguyen/rhq-psql
 
# Launch RHQ server
docker run -dPit --link rhq-psql:db --name rhq-server ahovsepy/rhq-nodb
