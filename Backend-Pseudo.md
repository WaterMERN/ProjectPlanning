 # Backend Plan

 # Models Pseudo Code
- Trip Schema
    - require mongoose at the top
    - create schema that will include:
        - budget: number
        - cost: number
        - date: number
        - Totals for lodging, food, transport, other all with
            - title: string
            - cost: number
    - declare Trip SChema as a variable and export at the bottom

- Day Schema
    - require mongoose at the top
    - create schema that will include
        - date: number || string
        - Expenses (lodging, food, transport, other) all with
            - title: string
            - cost: number
        - will have to link to trip schema for a specific trip
    - declare Day Schema as a variable and export at the bottom

- User Schema
    - require mongoose at the top
    - create schema that will include
        - name: string
        - email: {type: string, required: true, unique: true}
        - password: {type: string, required: true}
        - timestamp: true
    - declare User Schema as a variable and export at the bottom