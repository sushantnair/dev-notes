# 1. PUT vs. PATCH
1. PUT = 100% replacement of the resource representation
   
3. PATCH = Partial modification of specific fields
   
4. PUT behavior:
    * Client sends complete new state
    * Server replaces entire resource data with what you send
    * Any fields not included are effectively removed/reset to defaults
    
4. PATCH behavior:
    * Client sends only changed fields
    * Server updates only those specific fields
    * Unchanged fields remain untouched
    
5. 100% replacement = 100% replacement of business data, NOT the resource identity
    
6. Why delete+recreate breaks:
  User ID 123 referenced by:<br>
    * Orders table (foreign key user_id)
    * Comments table 
    * Session tokens
    * External systems
  Delete+recreate → User gets new ID 124<br>
  Result: All references broken, data orphaned<br>

7. What PUT actually replaces:<br>
  ✅ Business fields (name, email, preferences, etc.)<br>
  ❌ Identity fields (ID, creation date, internal references)<br>
  ❌ System metadata (created_at, version numbers)<br>
  ❌ Relational integrity<br>
