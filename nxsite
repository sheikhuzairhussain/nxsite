#!/bin/sh

# Color variables
red=`tput setaf 1`
green=`tput setaf 2`
end=`tput sgr0`

# Checks if NGINX is installed
if [ ! -d "/etc/nginx/" ] 
then
    echo "Error: NGINX not installed." 
    exit 1
fi


case $1 in
	list)
		case $2 in
			all)
				# Lists all sites
				for site in "/etc/nginx/sites-available"/*
				do
				    echo $(basename $site)
				done
				;;

			enabled)
				# Lists enabled sites
				for site in "/etc/nginx/sites-enabled"/*
				do
				    echo $(basename $site)
				done
				;;
			*)
				# Help for invalid list argument
				echo "Invalid argument for ${green}list${end}"
				echo "Usage: nxsite list [all|enabled]"
		esac
		;;

	up)
		if [ ! -f "/etc/nginx/sites-available/$2" ] 
		then
		    echo "Error: Site $green$2$end not found." 
		    exit 2
		fi
		ln -sf "/etc/nginx/sites-available/$2" "/etc/nginx/sites-enabled/"
		echo "Site $green$2$end activated."
		exit 0
		;;

	down)
		if [ ! -L "/etc/nginx/sites-enabled/$2" ] 
		then
		    echo "Error: Site $green$2$end not found." 
		    exit 2
		fi
		rm "/etc/nginx/sites-enabled/$2"
		;;

	*)
		echo "${green}NXSite${end} is a site manager for ${green}NGINX${end}."
		echo "Usage: nxsite [up|down] <site-name>"
		echo "       nxsite list [all|enabled]"
		;;
esac