###平时遇到的bug
   
   // iPhone7 中遇到的无痕浏览的sessionStrage、localstrage的兼容性问题
   ```
   if (typeof sessionStorage === 'object') {
              try {
                  sessionStorage.setItem("key","value");
              } catch (e) {
                  Storage.prototype._setItem = Storage.prototype.setItem;
                  Storage.prototype.setItem = function() {};
              }
          }
   ```