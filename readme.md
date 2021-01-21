# DynamicQuerysGo

## __Intro__

_DynamicQuerysGo_ is a simple project written in go, whith the intent to simulate a GraphQL like experience, in terms of querys and mutations. Here a request is called an action, which represents both an mutation and an query, the main purpose of these _actions_ is to resolve actions/requests to function calls, in a quick and simple way.

## __Things to keep in mind__

Since DynamicQuerysGo is based arround json, conssider the following:

1. Since the values passed in the json content are js primitives, there are no integers, only float64.

1. The parameters passed in the "params" object, must be in the same order as the parameters in the go function, other wise it will throw out an error.

1. The functions endpoints should be written with the action & function calling in mind

## __Examples__

__Action of Read/Get type:__

    {
        "action": {
            "auth": "mh354kh2vhvqyeoavq5yq8q5yyjuqqy5",
            "func": [
                {
                    "call": "GetRegisto",
                    "params": [
                        // the params order matters!
                        "Registo123",
                        ["name", "id"]
                    ]
                }
            ],
            "returns": [
                "success",
                "id",
                "nome"
            ] // or nil
        }
    }