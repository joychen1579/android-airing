﻿# android-airing
this is android airing library


[![LatestVersion](https://img.shields.io/badge/LatestVersion-1.0.0-brightgreen.svg?style=plastic) ](https://github.com/LiangMaYong/android-airing/releases/tag/V1.0.0)

## Gradle
```
compile 'com.liangmayong.android:airing:$LatestVersion'
```
## Get start
1,observer
```
Airing.getDefault().observer(this).register("main", new OnAiringListener() {
    @Override
    public void onAiring(AiringContent content) {
        Toast.makeText(getApplicationContext(), content.toString(), Toast.LENGTH_SHORT).show();
    }
}).register("action", new OnAiringListener() {
    @Override
    public void onAiring(AiringContent content) {
        Toast.makeText(getApplicationContext(), content.toString(), Toast.LENGTH_SHORT).show();
    }
});
```
2,sender
```
//sendEmpty
Airing.getDefault().sender("main").sendEmpty();
//send what
Airing.getDefault().sender("main").send(1);
//send bundle
Airing.getDefault().sender("main").send(1,extras);
//send Event
//Event can only be transmitted within the process
Airing.getDefault().sender("main").sendEvent(...);
```
3,unregister
```
Airing.getDefault().observer(this).unregister();

or

Airing.unregisterAll(this);
```
##License
```
Copyright 2016 LiangMaYong

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
