## Pricing Plans - Backend

Develop the backend logic to handle pricing plans retrievals.

## Acceptance Criteria

### Requirements
- [ ] Retrieve available Subcriptions or Plans (Basic/Premium)
- [ ] Retrieve available features for each plan
- [ ] Retrieve features unavailable for the plan and rightly marked as unavailable
- [ ] Retrieve payment plans for the plan (Monthly/Annually)
- [ ] Modify specific plan to add or remove features
- [ ] Display available discount to a plan if available
- [ ] Each plan contains:
   - [ ] Plan name
   - [ ] Amount
   - [ ] Plan Type


### Plan Entity (Table)
 - id (Primary Key)
 - plan_name (String)
 - price (Decimal)
 - features (Array or JSON)
 

### Retrieve Pricing Plans

**Endpoint**: `/api/pricing/plans`
**Method**: [GET]
**Success Response**:
  ```
  {
     statusCode: 200,
     message: "success message",
     plans: [
        {
           plan_id: "Number",
           plan_name: "String",
           price: "Number",
           features: "Array"
        }
     ]
  }
  ```
  
**No plan Response**:
  ```
  {
     statusCode: 200,
     message: "success message",
     plans: []
  }
  ```
  
**Failure Response**:
  ```
  {
     statusCode: 500,
     message: "unable to retrieve plans"
  }
  ```

### Expected Outcome
- [ ] Plan Details should be retrieved from the backend with all required information
- [ ] Endpoint returns 200 even if there are no available plans
- [ ] Return an error with meaningful message to the user if error is encountered

### Unit Test
- [ ] Plan Details should be retrieved from the backend with all required information
- [ ] Endpoint returns 200 even if there are no available plans
- [ ] Return an error with meaningful message to the user if error is encountered

