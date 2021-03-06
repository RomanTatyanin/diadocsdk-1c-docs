UtdRevision
===========

Исправление универсального передаточного документа.
Является производным объектом от :doc:`Document`


.. rubric:: Свойства объекта

:Function:
  **Строка, чтение** - функция универсального передаточного документа. |UtdRevision-Function|_

:Grounds:
  **Строка, чтение** - основание документа

:Currency:
  **Число, чтение** - код валюты

:Total:
  **Число, чтение** - cумма по документу

:Vat:
  **Число, чтение** - cумма НДС по документу

:ConfirmationDate:
  **Дата и время, чтение** - дата и время подтверждения оператора передачи документа

:Status:
  **Строка, чтение** - текущий статус документа в Диадоке. :doc:`Возможные значения <./Enums/UTDStatus>`

:OriginalDocumentDate:
  **Дата, чтение** - дата первоначального документа

:OriginalDocumentNumber:
  **Строка, чтение** - номер первоначального документа

:AmendmentRequested:
  **Булево, чтение** - признак, был ли запрос на уточнение


.. rubric:: Методы

+---------------------------------------------+--------------------------------+----------------------------------+
| |UtdRevision-GetContent|_                   | |UtdRevision-GetBuyerContent|_ | |UtdRevision-SendReceiptsAsync|_ |
+---------------------------------------------+--------------------------------+----------------------------------+
| |UtdRevision-GetAmendmentRequestedComment|_ |                                |                                  |
+---------------------------------------------+--------------------------------+----------------------------------+

.. |UtdRevision-GetContent| replace:: GetContent()
.. |UtdRevision-GetBuyerContent| replace:: GetBuyerContent()
.. |UtdRevision-SendReceiptsAsync| replace:: SendReceiptsAsync()
.. |UtdRevision-GetAmendmentRequestedComment| replace:: GetAmendmentRequestedComment()


.. _UtdRevision-GetContent:
.. method:: UtdRevision.GetContent()

  Возвращает :doc:`представление контента титула продавца <UtdSellerContent>`

  .. deprecated:: 5.27.0
    Используйте :meth:`Document.GetDynamicContent`



.. _UtdRevision-GetBuyerContent:
.. method:: UtdRevision.GetBuyerContent()

  Возвращает :doc:`представление контента титула покупателя <UtdBuyerContent>`

  .. deprecated:: 5.27.0
    Используйте :meth:`Document.GetDynamicContent`



.. _UtdRevision-SendReceiptsAsync:
.. method:: UtdRevision.SendReceiptsAsync()

  Формирует и подписывает документы по регламентному документообороту УКД



.. _UtdRevision-GetAmendmentRequestedComment:
.. method:: UtdRevision.GetAmendmentRequestedComment()

  Возвращает комментарий к уведомлению об уточнении

  .. deprecated:: 5.20.3
    Используйте Используйте :meth:`Document.GetAnyComment` с типом ``AmendmentComment``


.. rubric:: Дополнительная информация

.. |UtdRevision-Function| replace:: Возможные значения
.. _UtdRevision-Function:

=================== ======================================================================================================================================================================================
Значения *Function* Описание
=================== ======================================================================================================================================================================================
СЧФ                 счет-фактура, применяемый при расчетах по налогу на добавленную стоимость
СЧФДОП              счет-фактура, применяемый при расчетах по налогу на добавленную стоимость, и документ об отгрузке товаров (выполнении работ), передаче имущественных прав (документ об оказании услуг)
ДОП                 документ об отгрузке товаров (выполнении работ), передаче имущественных прав (документ об оказании услуг)
=================== ======================================================================================================================================================================================
