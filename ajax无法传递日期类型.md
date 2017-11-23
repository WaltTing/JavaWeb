# ajax无法传递日期类型

SpringMVC+Ajax的数据传递方式，一开始写成 `@PathVariable("apply_date") Date apply_date`,后来半天传不过来，然后我单个属性作为参数传递，只有Date类型会报错，所以最终的解决方案是前端的String类型经过后台的转换储存到数据库中：

> SimpleDateFormat sdf=new SimpleDateFormat("yyyy-MM-dd");    
  Date apply_date1 = sdf.parse(apply_date);