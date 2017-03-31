####Javascript设计模式
    过程式编程
        function animateStart(){...};
        ...
        function animateStop(){...};
     
    创建可以保存状态并且具有一些仅对其内部状态进行操作的方法    
        var Anim = function(){...}
        
        Anim.prototype.start = function(){...};
        ...
        Anim.prototype.stop = function(){...};
        
    把类封装在一条声明中、
        var Anim = function(){...};
        Anim.prototype = {
            start ； function(){...},
            ...
            stop　：function(){...}
        }


###给类添加新方法
    Function.prototype.method = function(name,fn){
        this.prototype[name] = fn;
        return this;//添加this可以实现链式调用
    }
    var Anim = function(){...};
    Anim.method('start',function(){...});
    ...
    Anim.method('stop',function(){...});
    Function.prototype.method用于为类添加新方法
       
###链式调用       
       Function.prototype.method = function(name,fn){
           this.prototype[name] = fn;
           return this;//添加this可以实现链式调用
       }
       var Anim = function(){...};
       Anim.method('start',function(){...}).
       ...
       .('stop',function(){...});
       Function.prototype.method用于为类添加新方法
       
       
       
###用注释描述接口
       /*
       interface composite {
            function add(child);
            function remove(child);
            function getChild(index);
       }
       */
       /*
       interface FormItem {
            function save();
       }
       */
       var CompositeForm = function(id,method,action){
            ...
       }
       CompositeForm.prototype.add == function(child){
            ...
       }
       CompositeForm.prototype.remove == function(child){
            ...
      }
      CompositeForm.prototype.getChild == function(index){
            ...
      }
      CompositeForm.prototype.save == function(){
            ...
      }        