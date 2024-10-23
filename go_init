#!/bin/env bash

# get params to get project name
project_name=""

usage() {
	printf "Usage: $0 [project_name]"
}

# if no arguments pass print usage
if [ "$1" == "" ]; then
	usage
	exit 1
fi

while [ "$1" != "" ]; do
	case $1 in
	# windows)
	# 	windows_flag=true
	# 	;;
	# release)
	# 	release_flag=true
	# 	;;
	# clean)
	# 	clean_flag=true
	# 	;;
	*)
		project_name=$1
		;;
	esac
	shift
done

mkdir $project_name
cd $project_name
go mod init $project_name
mkdir src out
printf "out/" >.gitignore

printf "package main\nimport \"fmt\"\nfunc main(){\nfmt.Println(\"Hello World\")\n}" >src/main.go

printf "#!/bin/env bash\ngo build -o out/$project_name src/main.go" >build.sh
chmod +x build.sh
