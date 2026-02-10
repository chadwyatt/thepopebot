# Quick Fix Reference: Google Places Results Limit

## 🎯 Goal
Change from 5 results → Show all available results (20-60)

## 🔍 What to Look For

### Most Likely Culprits:

```javascript
// 1. Array slice limiting results
results.slice(0, 5)        // FIND THIS
results.splice(0, 5)       // OR THIS

// 2. API parameter limiting
maxResults: 5              // OR THIS
maxResultCount: 5          // OR THIS

// 3. In JSX/React render
{results.slice(0, 5).map(...)}  // OR THIS
```

## 🛠️ Quick Fixes

### Fix #1: Remove Slice (Most Common)
```javascript
// BEFORE:
const displayResults = results.slice(0, 5);

// AFTER:
const displayResults = results;
```

### Fix #2: Increase Limit
```javascript
// BEFORE:
.slice(0, 5)

// AFTER:
.slice(0, 20)  // or just remove .slice() entirely
```

### Fix #3: API Parameter
```javascript
// BEFORE:
const request = {
  query: searchQuery,
  maxResults: 5
};

// AFTER:
const request = {
  query: searchQuery,
  maxResults: 20  // or remove this line
};
```

## 📂 Where to Search

### Search Commands:
```bash
# Search for 5-result limits
grep -r "slice(0, 5)\|splice(0, 5)\|maxResults.*5" src/

# Find Google Places files
find src -type f -name "*.js*" -exec grep -l "places\|PlacesService" {} \;

# Check Netlify Functions
grep -r "places" netlify/functions/
```

### Likely File Names:
- `*Setup*.js` / `*Setup*.jsx`
- `*QuickSetup*.js` / `*QuickSetup*.jsx`
- `*BusinessSearch*.js`
- `*PlaceSearch*.js`
- `*GooglePlaces*.js`

### Likely Directories:
- `src/components/`
- `src/pages/`
- `netlify/functions/`
- `functions/`

## ✅ Testing

After making changes, verify:
1. Search returns more than 5 results ✓
2. UI scrolls properly ✓
3. No console errors ✓
4. Works on mobile ✓

## 📊 Google Places API Facts

| Metric | Value |
|--------|-------|
| Default results per query | 20 |
| Max with pagination | 60 (3 pages × 20) |
| Delay for next page | 2-3 seconds |

## 💡 Pro Tips

1. **Don't just search for "5"** - search for `.slice(0, 5)` specifically
2. **Check both frontend and backend** - limit could be in API call or UI rendering
3. **Look for pagination code** - might already exist but be unused
4. **Check git history** - someone may have added limit intentionally

## 🚀 Implementation Time

- **Simple fix** (remove slice): 5 minutes
- **With testing**: 15-30 minutes
- **Add pagination**: 1-2 hours

## 📝 Example PR Title

```
feat: increase Google Places search results from 5 to 20
```

## 🔗 Need More Details?

See `SOLUTION_GUIDE.md` for:
- Detailed implementation steps
- Pagination examples
- Error handling
- Full code examples

---

**Quick Start**: 
1. Search: `grep -r "slice(0, 5)" src/`
2. Find the line
3. Remove or change the 5
4. Test
5. Commit & PR

That's it! 🎉
