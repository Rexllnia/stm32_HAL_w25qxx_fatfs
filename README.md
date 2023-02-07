# stm32_HAL_w25qxx_fatfs
## stm32CubeMX fatfs配置
最大扇区大小4096
## 片选端口定义
#define SPI_CS_GPIO_Port GPIOB  
#define SPI_CS_Pin GPIO_PIN_9
## spi收发函数定义
void spi2_Transmit_one_byte(uint8_t _dataTx)  
{  
	HAL_SPI_Transmit(&hspi2,(uint8_t*) &_dataTx,1,HAL_MAX_DELAY);  
}  
uint8_t spi2_Receive_one_byte()  
{  
	uint16_t _dataRx;  
	HAL_SPI_Receive(&hspi2,(uint8_t*) &_dataRx, 1, HAL_MAX_DELAY);  
	return _dataRx;  
}  
