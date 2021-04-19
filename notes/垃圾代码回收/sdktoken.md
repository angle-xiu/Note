# sdktoken
```html
            <!-- 充值页 -->
            <div class="paying" data-bind="visible:isPaying" style="display: block;margin-top: 20px">
                <div class="form-group">
                    <span><b>账户信息&nbsp;>&nbsp;账户充值</b></span>
                </div>
                <div class="form-group row">
                    <span class="col-md-2"><b>充值账户</b></span>
                    <span class="col-md-10" data-bind="$root.user">7979@qq.com</span>
                </div>
                <div class="form-group row">
                    <span class="col-md-2"><b>可用额度</b></span>
                    <span class="col-md-10" data-bind="Number($root.canInvoice()/100).toFixed(2)">0.00</span>
                </div>
                <div class="form-group row">
                    <span class="col-md-2"><b>充值金额</b></span>
                    <div class="col-md-10 form-inline ui-col-center">
                    <input type="number"min="0" required data-bind="textInput:$root.money" class="form-control">元
                    </div>
                    <div class="row">
                        <b class="col-md-2"></b>
                        <div class="col-md-10 ui-txt-red" data-bind="validationMessage: money"style="padding-left: 30px">金额不能为空</div>
                    </div>
                </div>
                <div class="form-group row">
                    <span class="col-md-2"><b>支付方式</b></span>
                    <div class="col-md-10 form-inline">
                        <button type="button" class="ib ui-col-center pay-item btn pay-active ion-checkmark-circled"><span class="zf-icon icon"></span>支付宝</button>
                        <button type="button" class="ib ui-col-center pay-item btn"><span class="wx-icon icon"></span>微信</button>
                    </div>
                </div>
                <div class="row form-group">
                    <b class="col-md-2">&nbsp;</b>
                    <div class="ib col-md-10">
                        <span>交易过程中遇到交易限额的问题，请前往相应的网上银行进行调整</span>
                    </div>
                </div>
                <div class="row form-group">

                    <b class="col-md-2">&nbsp;</b>
                    <div class="ib col-md-10">

                        <button class="btn pay-btn ui-txt-white" data-bind="click:
                              $root.payNow" data-toggle="modal" data-target="#pay">立即充值</button>
                    </div>
                </div>
            </div>

```