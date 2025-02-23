# Filter Persons Function

## Problem Statement

You are given a `filterPersons` function that filters users based on their type (`user` or `admin`). The function should:

- Return `User[]` when `personType` is `'user'`.
- Return `Admin[]` when `personType` is `'admin'`.
- Accept a partial `User` or `Admin` type based on the `personType` argument.
- Exclude the `type` field from the filtering criteria.

## Solution

The function was originally implemented but required type improvements. The following changes were made:

1. **Function Overloads:**
   - Added specific overloads to ensure the correct return type based on `personType`.
   - If `personType` is `'user'`, the function now guarantees a return type of `User[]`.
   - If `personType` is `'admin'`, it returns `Admin[]`.

2. **Criteria Handling:**
   - Ensured that the `criteria` argument only accepts relevant fields for the given `personType`.
   - Used `Partial<User>` when filtering users and `Partial<Admin>` for admins.

3. **Type Safety Improvements:**
   - Excluded filtering by the `type` property to prevent unnecessary redundancy.
   - Strengthened TypeScript typings for better type inference and safety.

## Usage Example

```typescript
export const usersOfAge23 = filterPersons(persons, 'user', { age: 23 });
export const adminsOfAge23 = filterPersons(persons, 'admin', { age: 23 });

console.log('Users of age 23:');
usersOfAge23.forEach(logPerson);

console.log();

console.log('Admins of age 23:');
adminsOfAge23.forEach(logPerson);
```

### Code Sample

You can view the full code sample at the following link:
[Code Sample](https://docs.google.com/document/d/1wI-IJcXLkwh6IL6zpLGk9OvQR2ueqapGasyv5jVaTJE/edit?usp=sharing)

