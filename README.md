# YTMusic-API
How to use YouTube Music API?

```js
getContext = () => {
    const context = {};
    const data = ytcfg.data_.INNERTUBE_CONTEXT.client;

    delete data['userAgent'];
    delete data['visitorData'];

    data['experimentIds'] = [];
    data['experimentsToken'] = '';
    data['utcOffsetMinutes'] = 0;
    
    data['locationInfo'] = { locationPermissionAuthorizationStatus: 'LOCATION_PERMISSION_AUTHORIZATION_STATUS_UNSUPPORTED' };
    data['musicAppInfo'] = {
        "musicActivityMasterSwitch": "MUSIC_ACTIVITY_MASTER_SWITCH_INDETERMINATE",
        "musicLocationMasterSwitch": "MUSIC_LOCATION_MASTER_SWITCH_ENABLED",
        "pwaInstallabilityStatus": "PWA_INSTALLABILITY_STATUS_CAN_BE_INSTALLED"
    };

    context['client'] = data;
    context['request'] = {
        "internalExperimentFlags": [
            {
                "key": "force_music_enable_outertube_playlist_detail_browse",
                "value": "true"
            },
            {
                "key": "force_music_enable_outertube_album_detail_browse",
                "value": "true"
            },
            {
                "key": "force_music_enable_outertube_music_queue",
                "value": "true"
            },
            {
                "key": "force_music_enable_outertube_tastebuilder_browse",
                "value": "true"
            },
            {
                "key": "force_music_enable_outertube_search_suggestions",
                "value": "true"
            }
        ],
        "sessionIndex": 1
    };
    context['capabilities'] = {};
    context['clickTracking'] = {
        "clickTrackingParams": "CA0QucgBGAEiEwimqd_hq5zrAhX0mcIKHcIABZw="
    };
    context['activePlayers'] = [
        {
            "playerContextParams": "Q0FFU0FnZ0I="
        }
    ];
    context["user"] = {
        "enableSafetyMode": false
    };
    return context;
}
```


```js
getSuggest = () => {
    return {
        "validationStatus": "VALID",
        "parameterValidationStatus": "VALID_PARAMETERS",
        "clientName": "youtube-music",
        "searchMethod": "CLICKED_SUGGESTION",
        "inputMethod": "KEYBOARD",
        "originalQuery": "",
        "availableSuggestions": [
            {
                "index": 0,
                "type": 25
            },
            {
                "index": 1,
                "type": 25
            },
            {
                "index": 2,
                "type": 25
            },
            {
                "index": 3,
                "type": 25
            },
            {
                "index": 4,
                "type": 25
            },
            {
                "index": 5,
                "type": 25
            },
            {
                "index": 6,
                "type": 25
            }
        ],
        "zeroPrefixEnabled": true,
        "firstEditTimeMsec": 4290731,
        "lastEditTimeMsec": 4292763
    }
}
```

```js
getSearchData =(query = '') => {
    return {
        context: getContext(),
        query,
        suggestStats: getSuggest(),
    }
}
```
