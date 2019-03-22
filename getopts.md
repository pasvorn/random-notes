An example of how to use ```getopts``` shell built-in command to process shell arguments. 
The use of ```getopts``` is actually well-known with old-timers. 
However, new gens are usually cycled to ```agrc``` and ```argv```. 
Save some time and use the built-in. :)

```bash
 while getopt df: flag
    do
        case $flag in

            d)
                  echo debugging on
                  ;;
            f)
                 file=$OPTARG
                 echo filename is $file
                 ;;
            ?)
                exit
                ;;
        esac
   done
shift $(( OPTIND - 1 ))  # shift past the last flag or argument

echo parameters are $*
```
