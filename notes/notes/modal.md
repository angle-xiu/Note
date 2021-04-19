# modal
<!-- modal -->
<!-- 关闭确认 -->
            <div class="fade modal" id="warn_close" aria-hidden="true">
                <div class="modal-dialog">
                    <div class="modal-content">
                        <div class="modal-body">
                        <h3 style="text-align: center">确认关闭余额预警？</h3>
                        </div>
                        <div class="modal-footer ui-row-center">
                        <button type="button" class="btn btn-secondary" data-dismiss="modal">取消</button>
                        <button type="button" class="btn btn-primary" data-bind="">确认</button>
                    </div>
                    </div>
                </div>
            </div>
<!-- 修改 -->
            <div class="modal fade" id="modify" aria-hidden="true">
                <div class="modal-dialog">
                    <div class="modal-content">
                        <div class="modal-body ui-center">
                            <input type="text"class="ib col-md-6 form-control" data-bind="textInput:
                $root.alertMoney,non_negative:$root.alertMoney" required placeholder="请输入预警金额">
                            <p>金额低于该值会发送短信或者邮箱提醒</p>
                        </div>
                        <div class="modal-footer ui-row-center">
                            <button type="button" class="btn" data-bind="click: $root.changeAlertMoney">提交</button>
                        </div>
                    </div>
                </div>
            </div>
<!-- 充值确认 -->
            <div class="modal fade" id="pay" tabindex="-1" role="dialog" aria-hidden="true">
                <div class="modal-dialog" role="document">
                    <div class="modal-content">
                        <div class="modal-header">
                            <h5 class="modal-title" >确认充值</h5>
                            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                                <span aria-hidden="true">&times;</span>
                            </button>
                        </div>
                        <div class="modal-body row">
                            <div class="col-md-offset-3 col-md-6">
                            <div class="form-group row">
                                <b class="col-md-6">充值方式：</b>
                                <div class="col-md-6" data-bind="if:payItem == 1">
                                    <span class="zf-icon icon" style="width: 24px;height: 24px;"></span>支付宝
                                </div>
                                <div class="col-md-6" data-bind="if:payItem == 2" style="display: none;">
                                    <span class="wx-icon icon" style="width: 24px;height: 24px;"></span>微信
                                </div>
                            </div>
                            <div class="form-group row">
                                <b class="col-md-6">充值到账：</b>
                                <span class="col-md-6" data-bind="text:">￥123.00</span>
                            </div>
                            <div class="form-group row">
                                <b class="col-md-6">实际到账：</b>
                                <span class="col-md-6" data-bind="text:">￥123.00</span>
                            </div>
                            </div>
                        </div>
                        <div class="modal-footer ui-row-center">
                            <button type="button" class="btn btn-secondary" data-dismiss="modal">取消</button>
                            <button type="button" class="btn btn-primary" data-bind="">去支付</button>
                        </div>
                    </div>
                </div>
            </div>
<!-- demo -->