# this is New supper fast Mikrotik Scripting way

## old Way = 
### Get Active Address;

{
:local Id [/ip hotspot active find user="test"];

:if ([:len $Id]>0) do={

:local Address [/ip hotspot active get $Id address]; 

:put $Address

}
}

## old Way = 
### Get Active Address fast;

:foreach i in=[/ip hotspot active find user="test"] do={

:local Address [/ip hotspot active get $i address];

:put $Address;

};

## old Way = 
### Get Active Address very fast;

{

:local AC [/ip hotspot active print as-value where user="test"];

:local Address ($AC->("address"));

:put $Address;
}


## My NEW Supper Fasssssssssssssssst Way 

/ip hotspot active find [:if ($user="test") do={:put $address;}];

### BOOOOOM ....
### Can You Imagine 

#You Could Do Any Thing insid do={ ...  }

/ip hotspot active find [:if (user="test" && mac-address!="44:33:33:22:11:00:33") do={/log info ("Active Removed the user id=".$".id");remove $".id";}];


### and So On ...............

http://wwww.fb.com/osamahfarhan



