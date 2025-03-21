| **Page / Feature** | **Guest** | **Reserver** | **Administrator** | **Notes** |
|:----|:----:|:----:|:----:|:----:|
| `/`               | | | |
| └─ View resource form      | ✅ | ✅ | ✅ | - |
| └─ booked resources show the reserver's identity   | ❌ | ✅ | ✅ | - |
| `/resources`               | | | |
| └─ Create new resource     | ⚠️ No | ✅| ✅ | Guest can add add new resource by accessing the resource page by adding the address to url! |
| `/resources?id=2`               | | | |
| └─ Modify resource     | ❌ | ⚠️ No | ✅ | Reserver can modify a resource by accessing page by adding the address (/resources?id=2) to url |
| └─ Remove a resource     | ❌ | ❌ | ❌ | Not implemented/Not possible to empty the fields and save |
| `/reservation`               | | | |
| └─ Create new reservation     | ❌ | ⚠️ Yes, but only if age over 15 | ⚠️ Yes, but only if age over 15 | - |
| └─ Modify reservation     | ❌ | ❌ | ✅ | - |
| └─ Remove a reservation     | ❌ | ❌ | ❌ | Not implemented|
| `/profile`                 | | | |
| └─ View own profile      | ❌ | ❌ | ❌ | Not implemented |
| `/login`                 | | | |
| └─ Login     | ✅ | ❌ | ❌ | Reserver and administrator can acces the register page by adding address to url-|
| `/register`                | | | |
| └─ Register    | ✅ | ❌ | ❌ | Reserver and administrator can acces the register page by adding address to url |
| `/admin/users`                | | | |
| └─ Remove the reserver     | ❌ | ❌ | ❌ | Not implemented |
| `/admin/settings`                | | | |
| └─ Change settings     | ❌ | ❌ | ❌ | Not implemented |
| `/logout`                | | | |
| └─ Logout     | ❌ | ✅ | ✅ | User can't see a separate page for logout, but it will happen when user click's logout-button |


**Symbols used:**  
✅ Pass (a note can be added)  
❌ Fail (a note can be added)  
⚠️ Attention (a note can be added)

---
**Zap raport in the separate file**

---

## 5. Third testing technique: wfuzz and http
**What kind of pages can be found using common words?**
- Found in addition to the previous ones the page /logout

**Is there an API folder and pages under it?**
- Resources, session, users

**Are there any pages in the reservations folder whose name is a number between 1-1000?**
- Yes, there is a lot of them starting from 30

**When the page is found, then what the page contains?**
- The page contains the information of specific reservation, including token of reserver