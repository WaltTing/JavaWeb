# Mybatis 动态sql

Mybatis 动态标签sql和include：   
sql用来封装sql语句，\<include>用来调用sql语句。如


    <sql id="select">
		SELECT * FROM test
	</sql>

	<sql id="query">
		<if test="query !=null">
			<where>
				<if test="query.id !=null">
					AND id = #{query.id}
				</if>
			</where>
		</if>
	</sql>

	<sql id="timeDesc">
		ORDER BY `time` DESC
	</sql> 

	<sql id="limit">
		<if test="query.limit !=null">
			LIMIT #{query.limit}
		</if>
	</sql>

	<select id="find" resultType="*" resultMap="*">
		<include refid="select"></include>
		<include refid="query"></include>
		<include refid="timeDesc"></include>
		<include refid="limit"></include>
	</select>

参考： http://blog.csdn.net/baidu_31657889/article/details/52101130