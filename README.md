# TranslateManager
Библиотека - это некий самодостаточный код который выполняет строго возложенные на него обязательства.
1. TranslateManager должен возвращать переводы из указанных сервисов. Пока только Google.
2. Должна быть поддержка адаптеров. Для того, чтобы мы могли использовать любой сервис отличный от Google.
3. У нас должен быть менеджур в который можно установить необходимый адаптер для переводов.
3.1. Менеджер должен иметь метод translate(слово_которое_хотим_перевести, язык_перевода)
3.2. Обязательно должна быть возможность переводить на любые языки.

Писать как можно меньше кода. Из этого получается более понятный код. Более читабельный. Проще модифицируемый.

$manager = new Manager();
$manager->setAdapter(new Google());
$translateRu = $manager->translate('hello', 'ru');
$translateUa = $manager->translate('hello', 'ua');
$translateUa = $manager->translate('hello', 'de');
$translateUa = $manager->translate('hello', 'gr');


$manager = new Manager();
$manager->setAdapter(new Google('ru'));
$translateRu = $manager->translate('hello');
$manager->setAdapter(new Google('ua'));
$translateUa = $manager->translate('hello');
$manager->setAdapter(new Google('de'));
$translateUa = $manager->translate('hello');
$manager->setAdapter(new Google('gr'));
$translateUa = $manager->translate('hello');