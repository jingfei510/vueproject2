<template>
	<div>
		<div style="border: gainsboro solid 1px; width: 80%; height: 100%;margin-left: 10%; ">
<div style="margin-bottom: 30px;"></div>
			<el-form ref="form" :model="form" label-width="80px">

				<el-form-item label="姓名" style="width: 200px; display: inline;" class="sex">
					<el-input v-model="form.name" style="width: 200px;"></el-input>
				</el-form-item>

				<el-form-item label="性别" class="sex">
					<el-radio-group v-model="form.sex">
						<el-radio label="男"></el-radio>
						<el-radio label="女"></el-radio>
					</el-radio-group>
				</el-form-item>

				<el-form-item label="出生年月" class="sex">
					<el-date-picker v-model="form.birth" type="date" placeholder="选择日期">
					</el-date-picker>
				</el-form-item>

				<div class="clear"></div>

				<el-form-item label="联系电话" class="sex">
					<el-input v-model="form.telephone"></el-input>
				</el-form-item>
				<el-form-item label="身份证号" class="sex">
					<el-input v-model="form.idCard"></el-input>
				</el-form-item>


				<div class="clear"></div>

				<el-form-item label="家庭住址" class="sex">
					<el-input v-model="form.address"></el-input>
				</el-form-item>
				<el-form-item label="紧急联系" class="sex">
					<el-input v-model="form.telephone1"></el-input>
				</el-form-item>
				<div class="clear"></div>

				<el-form-item label="过敏药物" class="sex">
					<el-checkbox-group v-model="form.forbiddenType">
						<el-checkbox label="头孢菌素类药物" name="type"></el-checkbox>
						<el-checkbox label="碳青霉烯类药物" name="type"></el-checkbox>
						<el-checkbox label="糖肽类药物" name="type"></el-checkbox>
						<el-checkbox label="磺胺类药物" name="type"></el-checkbox>
					</el-checkbox-group>
				</el-form-item>

				<el-form-item label="备注" style="float: left; margin-left: 80px;">
					<el-input v-model="form.forbiddenMedicine"></el-input>
				</el-form-item>
				<div class="clear"></div>
				<div style="border: gainsboro dashed 1px;"></div>

				<el-form-item label="病历一:" style="margin-left: 80px;"></el-form-item>
				<el-form-item label="就诊医院" class="sex">
					<el-select v-model="form.medicalHistory.selectHospital1" placeholder="--请选择--">
						<el-option label="咸阳第一附属医院" value="咸阳第一附属医院"></el-option>
						<el-option label="咸阳第二附属医院" value="咸阳第二附属医院"></el-option>
						<el-option label="咸阳中心医院" value="咸阳中心医院"></el-option>
					</el-select>
				</el-form-item>

				<el-form-item label="就诊时间 " class="sex">
					<el-col :span="11">
						<el-date-picker type="date" placeholder="选择日期" v-model="form.medicalHistory.date1_1" style="width: 100%;"></el-date-picker>
					</el-col>
					<el-col class="line" :span="2">-</el-col>
					<el-col :span="11">
						<el-time-picker placeholder="选择时间" v-model="form.medicalHistory.date1_2" style="width: 100%;"></el-time-picker>
					</el-col>
				</el-form-item>

				<el-form-item label="主治医师" class="sex">
					<el-input v-model="form.medicalHistory.doctorName1" style="width: 200px;"></el-input>
				</el-form-item>

				<div class="clear"></div>

				<el-form-item label="入院状况" class="sex">
					<el-input v-model="form.medicalHistory.condition1"></el-input>
				</el-form-item>

				<el-form-item label="是否住院" class="sex">
					<el-radio-group v-model="form.medicalHistory.inHospital1">
						<el-radio label="是"></el-radio>
						<el-radio label="否"></el-radio>
					</el-radio-group>
				</el-form-item>

				<div class="clear"></div>

				<el-form-item label="检查项目" class="sex">
					<el-input v-model="form.medicalHistory.checkName1"></el-input>
				</el-form-item>
				<el-form-item label="检查结果" class="sex">
					<el-input v-model="form.medicalHistory.checkResult1" style="width: 200px;"></el-input>
				</el-form-item>
				
				<div class="clear"></div>
				
				<el-form-item label="医生治疗方案" label-width="110px" class="sex1">
					<el-input type="textarea" v-model="form.medicalHistory.finallycheckResult1"></el-input>
				</el-form-item>

				<el-form-item label="病历二:" style="margin-left: 80px;"></el-form-item>
				<el-form-item label="就诊医院" class="sex">
					<el-select v-model="form.medicalHistory.selectHospital2" placeholder="--请选择--">
						<el-option label="咸阳第一附属医院" value="咸阳第一附属医院"></el-option>
						<el-option label="咸阳第二附属医院" value="咸阳第二附属医院"></el-option>
						<el-option label="咸阳中心医院" value="咸阳中心医院"></el-option>
					</el-select>
				</el-form-item>

				<el-form-item label="就诊时间 " class="sex">
					<el-col :span="11">
						<el-date-picker type="date" placeholder="选择日期" v-model="form.medicalHistory.date2_1" style="width: 100%;"></el-date-picker>
					</el-col>
					<el-col class="line" :span="2">-</el-col>
					<el-col :span="11">
						<el-time-picker placeholder="选择时间" v-model="form.medicalHistory.date2_2" style="width: 100%;"></el-time-picker>
					</el-col>
				</el-form-item>

				<el-form-item label="主治医师" class="sex">
					<el-input v-model="form.medicalHistory.doctorName2" style="width: 200px;"></el-input>
				</el-form-item>

				<div class="clear"></div>

				<el-form-item label="入院状况" class="sex">
					<el-input v-model="form.medicalHistory.condition2"></el-input>
				</el-form-item>

				<el-form-item label="是否住院" class="sex">
					<el-radio-group v-model="form.medicalHistory.inHospital2">
						<el-radio label="是"></el-radio>
						<el-radio label="否"></el-radio>
					</el-radio-group>
				</el-form-item>

				<div class="clear"></div>

				<el-form-item label="检查项目" class="sex">
					<el-input v-model="form.medicalHistory.checkName2"></el-input>
				</el-form-item>
				<el-form-item label="检查结果" class="sex">
					<el-input v-model="form.medicalHistory.checkResult2" style="width: 200px;"></el-input>
				</el-form-item>
				
				<div class="clear"></div>
				
				<el-form-item label="医生治疗方案" label-width="110px" class="sex1">
					<el-input type="textarea" v-model="form.medicalHistory.finallycheckResult2"></el-input>
				</el-form-item>


				<el-form-item>
					<el-button type="primary" @click="onSubmit">立即上传</el-button>
					<el-button>取消</el-button>
				</el-form-item>
			</el-form>
			<!-- <div @click="aaa" class="aaa">aaa</div> -->
		</div>
	</div>
</template>

<script>
	import '../style.css'
	export default {
		data() {
			return {
				form: {
					name: '',
					sex: '',
					birth: '',
					telephone: '',
					idCard: '',
					telephone1: '',
					forbiddenType: [],
					forbiddenMedicine: '',

					medicalHistory: {
						selectHospital1: '',
						date1_1: '',
						date1_2: '',
						doctorName1: '',
						condition1: '',
						inHospital1: '',
						checkName1: '',
						checkResult1: '',
						finallycheckResult1: '',
						selectHospital2: '',
						date2_1: '',
						date2_2: '',
						doctorName2: '',
						condition2: '',
						inHospital2: '',
						checkName2: '',
						checkResult2: '',
						finallycheckResult2: ''
					}

				}
			}
		},
		methods: {
			onSubmit() {
				console.log(this.form)
				alert("提交成功！")
			},
			aaa() {
				console.log($('.aaa')[0].innerText)
			}
		},
	}
</script>
