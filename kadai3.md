```uml
@startuml
start
:weather;
if(weather==0) then (true)
:快晴です;
if(weather==1) then (true)
:曇りです;
if(weather==2) then (true)
:雨です;
else(false)
:不明;
endif
end
```
