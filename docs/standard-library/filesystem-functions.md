---
title: '&lt;filesystem&gt; 함수'
ms.date: 03/27/2019
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::absolute
- FILESYSTEM/std::experimental::filesystem::canonical
- FILESYSTEM/std::experimental::filesystem::copy
- FILESYSTEM/std::experimental::filesystem::copy_file
- FILESYSTEM/std::experimental::filesystem::copy_symlink
- FILESYSTEM/std::experimental::filesystem::create_directories
- FILESYSTEM/std::experimental::filesystem::create_directory
- FILESYSTEM/std::experimental::filesystem::create_directory_symlink
- FILESYSTEM/std::experimental::filesystem::create_hard_link
- FILESYSTEM/std::experimental::filesystem::create_symlink
- FILESYSTEM/std::experimental::filesystem::current_path
- FILESYSTEM/std::experimental::filesystem::equivalent
- FILESYSTEM/std::experimental::filesystem::exists
- FILESYSTEM/std::experimental::filesystem::file_size
- FILESYSTEM/std::experimental::filesystem::hard_link_count
- FILESYSTEM/std::experimental::filesystem::hash_value
- FILESYSTEM/std::experimental::filesystem::is_block_file
- FILESYSTEM/std::experimental::filesystem::is_character_file
- FILESYSTEM/std::experimental::filesystem::is_directory
- FILESYSTEM/std::experimental::filesystem::is_empty
- FILESYSTEM/std::experimental::filesystem::is_fifo
- FILESYSTEM/std::experimental::filesystem::is_other
- FILESYSTEM/std::experimental::filesystem::is_regular_file
- FILESYSTEM/std::experimental::filesystem::is_socket
- FILESYSTEM/std::experimental::filesystem::is_symlink
- FILESYSTEM/std::experimental::filesystem::last_write_time
- FILESYSTEM/std::experimental::filesystem::permissions
- FILESYSTEM/std::experimental::filesystem::read_symlink
- FILESYSTEM/std::experimental::filesystem::remove
- FILESYSTEM/std::experimental::filesystem::remove_all
- FILESYSTEM/std::experimental::filesystem::rename
- FILESYSTEM/std::experimental::filesystem::resize_file
- FILESYSTEM/std::experimental::filesystem::space
- FILESYSTEM/std::experimental::filesystem::status
- FILESYSTEM/std::experimental::filesystem::status_known
- FILESYSTEM/std::experimental::filesystem::swap
- FILESYSTEM/std::experimental::filesystem::symlink_status
- FILESYSTEM/std::experimental::filesystem::system_complete
- FILESYSTEM/std::experimental::filesystem::temp_directory_path
- FILESYSTEM/std::experimental::filesystem::u8path
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
helpviewer_keywords:
- std::experimental::filesystem::absolute
- std::experimental::filesystem::canonical
- std::experimental::filesystem::copy
- std::experimental::filesystem::copy_file
- std::experimental::filesystem::copy_symlink
- std::experimental::filesystem::create_directories
- std::experimental::filesystem::create_directory
- std::experimental::filesystem::create_directory_symlink
- std::experimental::filesystem::create_hard_link
- std::experimental::filesystem::create_symlink
- std::experimental::filesystem::current_path
- std::experimental::filesystem::equivalent
- std::experimental::filesystem::exists
- std::experimental::filesystem::file_size
- std::experimental::filesystem::hard_link_count
- std::experimental::filesystem::hash_value
- std::experimental::filesystem::is_block_file
- std::experimental::filesystem::is_character_file
- std::experimental::filesystem::is_directory
- std::experimental::filesystem::is_empty
- std::experimental::filesystem::is_fifo
- std::experimental::filesystem::is_other
- std::experimental::filesystem::is_regular_file
- std::experimental::filesystem::is_socket
- std::experimental::filesystem::is_symlink
- std::experimental::filesystem::last_write_time
- std::experimental::filesystem::permissions
- std::experimental::filesystem::read_symlink
- std::experimental::filesystem::remove
- std::experimental::filesystem::remove_all
- std::experimental::filesystem::rename
- std::experimental::filesystem::resize_file
- std::experimental::filesystem::space
- std::experimental::filesystem::status
- std::experimental::filesystem::status_known
- std::experimental::filesystem::swap
- std::experimental::filesystem::symlink_status
- std::experimental::filesystem::system_complete
- std::experimental::filesystem::temp_directory_path
- std::experimental::filesystem::u8path
ms.openlocfilehash: f1b48ed6f533d4ccb5f9ef5e6dbcbd6e5cc4f7a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332044"
---
# <a name="ltfilesystemgt-functions"></a>&lt;filesystem&gt; 함수

[ \<헤더가](../standard-library/filesystem.md) 경로, 파일, 심볼링크, 디렉터리 및 볼륨에서 작업을 수정하고 쿼리할>파일 시스템의 이러한 무료 함수입니다. 자세한 정보 및 코드 예제는 [파일 시스템 탐색(C++)을](../standard-library/file-system-navigation.md)참조하십시오.

## <a name="absolute"></a><a name="absolute"></a>절대

```cpp
path absolute(const path& pval, const path& base = current_path());
```

함수는 pathname을 기준으로 *pval에* 해당하는 절대 `base`경로 이름을 반환합니다.

1. 함수가 `pval.has_root_name() && pval.has_root_directory()` *pval을*반환하는 경우 .

1. 함수가 반환되는 `pval.has_root_name() && !pval.has_root_directory()` `pval.root_name()`  /  `absolute(base).root_directory()`  /  `absolute(base).relative_path()`  / 경우 . `pval.relative_path()`

1. 함수가 `!pval.has_root_name() && pval.has_root_directory()` `absolute(base).root_name()`  /  *pval을*반환하는 경우 .

1. 함수가 `!pval.has_root_name() && !pval.has_root_directory()` `absolute(base)`  /  *pval을*반환하는 경우 .

## <a name="begin"></a><a name="begin"></a>시작

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

두 함수 모두 *이터.*

## <a name="canonical"></a><a name="canonical"></a>정식

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

함수는 모두 절대 경로 `pabs = absolute(pval, base)` 이름(또는 `pabs = absolute(pval)` 기본 매개 변수가 없는 오버로드)을 형성한 다음 다음 단계 시퀀스에서 표준 형식으로 축소합니다.

1. true인 `X` 모든 경로 구성 요소는 `read_symlink(X)`로 대체됩니다. **true** `is_symlink(X)`

1. 모든 경로 `.` 구성 요소(점은 이전 경로 구성 요소에 의해 설정된 현재 디렉터리)가 제거됩니다.

1. 모든 경로 구성 `X` / `..` 요소 쌍(점은 이전 경로 구성 요소에 의해 설정된 상위 디렉터리)이 제거됩니다.

그러면 함수가 반환됩니다. `pabs`

## <a name="copy"></a><a name="copy"></a>복사

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

이 함수는 모두 옵트 매개 변수없이 *from* `copy_options::none` 오버로드에 대해 수행되는 *opts의* *제어하에* 하나 이상의 파일을 복사하거나 *연결합니다.* *opts는* 다음 중 하나를 포함해야 합니다.

- `skip_existing`, `overwrite_existing` 또는 `update_existing`

- `copy_symlinks` 또는 `skip_symlinks`

- `directories_only`, `create_symlinks` 또는 `create_hard_links`

함수는 먼저 *다음의* `t` `f` file_status 값을 *to*결정합니다.

- if `opts & (copy_options::create_symlinks | copy_options::skip_symlinks)`.`symlink_status`

- 그렇지 않으면, 전화로`status`

- 그렇지 않으면 오류를 보고합니다.

If `!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)`, 그들은 오류를보고합니다 (그리고 다른 것은 하지 않습니다).

그렇지 않으면 `is_symlink(f)` 다음을 수행합니다.

- IF `options & copy_options::skip_symlinks`, 다음 아무것도하지 않습니다.

- 그렇지 않으면 `!exists(t)&& options & copy_options::copy_symlinks`. `copy_symlink(from, to, opts)`

- 그렇지 않으면 오류를 보고합니다.

그렇지 않으면 `is_regular_file(f)`다음과 같은 경우

- IF `opts & copy_options::directories_only`, 다음 아무것도하지 않습니다.

- 그렇지 않으면 `opts & copy_options::create_symlinks`. `create_symlink(to, from)`

- 그렇지 않으면 `opts & copy_options::create_hard_links`. `create_hard_link(to, from)`

- 그렇지 않으면 `is_directory(f)`. `copy_file(from, to`  /  `from.filename(), opts)`

- 그렇지 않으면 `copy_file(from, to, opts)`입니다.

그렇지 않으면 `is_directory(f) && (opts & copy_options::recursive || !opts)`다음과 같은 경우

```cpp
if (!exists(t))
{  // copy directory contents recursively
    create_directory(to, from, ec);

    for (directory_iterator next(from), end; ec == error_code() && next != end; ++next)
    {
        copy(next->path(), to / next->path().filename(), opts, ec);
    }
}
```

그렇지 않으면 아무 작업도 수행하지 않습니다.

## <a name="copy_file"></a><a name="copy_file"></a>copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

함수는 모두 옵트 매개 *from* 변수없이 오버로드에 대해 `copy_options::none` 수행되는 *opts의* *제어하에* 파일을 복사 할 수 *있습니다.* *opts는* 에 대한 `skip_existing`가장 `overwrite_existing`큰 `update_existing`포함을 해야 합니다.

다음 `exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))`파일이 이미 있는 오류로 보고합니다.

그렇지 않으면 `!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))`파일의 내용과 특성을 *파일에서* 로 복사하려고 *시도합니다.* 복사 시도가 실패하는 경우 오류로 보고합니다.

함수는 복사본을 시도하고 성공하는 경우 **true를** **반환합니다.**

## <a name="copy_symlink"></a><a name="copy_symlink"></a>copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

이 `is_directory(from)`함수가 `create_directory_symlink(from, to)`호출하는 경우 . 그렇지 않으면 `create_symlink(from, to)`합니다.

## <a name="create_directories"></a><a name="create_directories"></a>create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

\/b\/c와 같은 경로 이름의 경우 함수는 필요에\/따라 디렉토리 a와 b를\/만들어\/필요에 따라 디렉터리 a c를 만들 수 있습니다. 실제로 디렉터리 *pval을*만드는 경우에만 **true를** 반환합니다.

## <a name="create_directory"></a><a name="create_directory"></a>create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

함수는 필요에 따라 디렉터리 *pval을* 만듭니다. 실제로 디렉터리 *pval을*만드는 경우에만 true를 반환하며, 이 경우 기존 파일 *attr에서*사용 권한을 복사하거나 `perms::all` *attr* 매개 변수가 없는 오버로드에 사용합니다.

## <a name="create_directory_symlink"></a><a name="create_directory_symlink"></a>create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

함수는 *에*대한 디렉터리에 대한 심볼링크로 링크를 만듭니다.

## <a name="create_hard_link"></a><a name="create_hard_link"></a>create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

함수는 디렉터리 또는 *파일에*대한 하드 링크로 링크를 만듭니다.

## <a name="create_symlink"></a><a name="create_symlink"></a>create_symlink

```cpp
void create_symlink(const path& to, const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

이 함수는 *파일에*대한 심볼링크로 *링크를* 만듭니다.

## <a name="current_path"></a><a name="current_path"></a>current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

매개 변수 *pval이* 없는 함수는 현재 디렉터리에 대한 pathname을 반환합니다. 나머지 함수는 현재 디렉터리를 *pval으로*설정합니다.

## <a name="end"></a><a name="end"></a>끝

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

첫 번째 `directory_iterator()` 함수가 반환되고 두 번째 함수가 반환됩니다.`recursive_directory_iterator()`

## <a name="equivalent"></a><a name="equivalent"></a>해당

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

함수는 *왼쪽과* *오른쪽이* 동일한 파일 시스템 엔터티를 선택하는 경우에만 **true를** 반환합니다.

## <a name="exists"></a><a name="exists"></a>존재

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `status_known && stat.type() != file_not_found`를 반환합니다. 두 번째 및 세 `exists(status(pval))`번째 함수가 반환됩니다.

## <a name="file_size"></a><a name="file_size"></a>file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

함수는 *pval에*의해 선택된 파일의 바이트 크기로 크기를 반환합니다. `exists(pval) && is_regular_file(pval)` 그렇지 않으면 오류를 보고하고 반환합니다. `uintmax_t(-1)`

## <a name="hard_link_count"></a><a name="hard_link_count"></a>hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

함수는 *pval에*대한 하드 링크 \-수 또는 오류가 발생하는 경우 1을 반환합니다.

## <a name="hash_value"></a><a name="hash_value"></a>hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

함수는 에 대한 `pval.native()`해시 값을 반환합니다.

## <a name="is_block_file"></a><a name="is_block_file"></a>is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::block`를 반환합니다. 나머지 함수는 `is_block_file(status(pval))`반환합니다.

## <a name="is_character_file"></a><a name="is_character_file"></a>is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::character`를 반환합니다. 나머지 함수는 `is_character_file(status(pval))`반환합니다.

## <a name="is_directory"></a><a name="is_directory"></a>is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::directory`를 반환합니다. 나머지 함수는 `is_directory_file(status(pval))`반환합니다.

## <a name="is_empty"></a><a name="is_empty"></a>is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

이 `is_directory(pval)`함수가 반환되는 `directory_iterator(pval) == directory_iterator()`경우 . 그렇지 않으면 `file_size(pval) == 0`반환합니다.

## <a name="is_fifo"></a><a name="is_fifo"></a>is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::fifo`를 반환합니다. 나머지 함수는 `is_fifo(status(pval))`반환합니다.

## <a name="is_other"></a><a name="is_other"></a>is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::other`를 반환합니다. 나머지 함수는 `is_other(status(pval))`반환합니다.

## <a name="is_regular_file"></a><a name="is_regular_file"></a>is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::regular`를 반환합니다. 나머지 함수는 `is_regular_file(status(pval))`반환합니다.

## <a name="is_socket"></a><a name="is_socket"></a>is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::socket`를 반환합니다. 나머지 함수는 `is_socket(status(pval))`반환합니다.

## <a name="is_symlink"></a><a name="is_symlink"></a>is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::symlink`를 반환합니다. 나머지 함수는 `is_symlink(status(pval))`반환합니다.

## <a name="last_write_time"></a><a name="last_write_time"></a>last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

처음 두 함수는 *pval에*대한 마지막 데이터 `file_time_type(-1)` 수정 시간을 반환하거나 오류가 발생하는 경우 를 반환합니다. 마지막 두 함수는 *pval이* *new_time*마지막 데이터 수정 시간을 설정합니다.

## <a name="permissions"></a><a name="permissions"></a>권한을

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

함수는 *pval에서* 선택한 경로 이름에 대한 사용 `mask & perms::mask` 권한을 `perms & (perms::add_perms | perms::remove_perms)`을 제어하도록 설정합니다. *마스크는* 의 대부분을 `perms::add_perms` 포함해야한다. `perms::remove_perms`

이 `mask & perms::add_perms`함수가 권한을 로 설정하면 `status(pval).permissions() | mask & perms::mask`에 대한 사용 권한이 설정됩니다. 그렇지 않으면 `mask & perms::remove_perms`함수가 에 대한 사용 `status(pval).permissions() & ~(mask & perms::mask)`권한을 설정합니다. 그렇지 않으면 함수가 권한을 `mask & perms::mask`로 설정합니다.

## <a name="proximate"></a><a name="proximate"></a>공업

```cpp
path proximate(const path& p, error_code& ec);
path proximate(const path& p, const path& base = current_path());
path proximate(const path& p, const path& base, error_code& ec);
```

## <a name="read_symlink"></a><a name="read_symlink"></a>read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

함수는 오류를 보고하고 `path()` 다음을 `!is_symlink(pval)`반환합니다. 그렇지 않은 경우 함수는 기호 링크를 포함하는 `path` 형식의 개체를 반환합니다.

## <a name="relative"></a><a name="relative"></a>상대

```cpp
path relative(const path& p, error_code& ec);
path relative(const path& p, const path& base = current_path());
path relative(const path& p, const path& base, error_code& ec);
```

## <a name="remove"></a><a name="remove"></a>제거

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

함수는 파일이 성공적으로 `exists(symlink_status(pval))` 제거된 경우에만 **true를** 반환합니다. 심볼링크자체는 선택한 파일이 아니라 제거됩니다.

## <a name="remove_all"></a><a name="remove_all"></a>remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

*pval이* 디렉터리인 경우 함수는 모든 디렉터리 항목을 재귀적으로 제거한 다음 항목 자체를 제거합니다. 그렇지 않으면 함수가 `remove`을 호출합니다. 함수는 성공적으로 제거된 모든 요소의 수를 반환합니다.

## <a name="rename"></a><a name="rename"></a>이름을 바꿀

```cpp
void rename(const path& from, const path& to);
void rename(const path& from, const path& to, error_code& ec) noexcept;
```

함수의 이름이 *에서* *로*바꿉니다. 심볼링크는 선택한 파일이 아니라 이름이 바뀝니다.

## <a name="resize_file"></a><a name="resize_file"></a>resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

함수는 파일의 크기를 변경하여`file_size(pval) == size`

## <a name="space"></a><a name="space"></a>공간

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

함수는 *pval에서*선택한 볼륨에 대한 정보를 형식 `space_info`구조로 반환합니다. 구조에는 `uintmax_t(-1)` 확인할 수 없는 값에 대한 내용이 포함되어 있습니다.

## <a name="status"></a><a name="status"></a>상태

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

함수는 *pval*과 연결된 pathname 상태, 파일 형식 및 사용 권한을 반환합니다. 심볼링크 자체는 테스트되지 않지만 선택한 파일입니다.

## <a name="status_known"></a><a name="status_known"></a>status_known

```cpp
bool status_known(file_status stat) noexcept;
```

함수가 반환됩니다.`stat.type() != file_type::none`

## <a name="swap"></a><a name="swap"></a>스왑

```cpp
void swap(path& left, path& right) noexcept;
```

기능은 *좌우의* 내용을 *교환합니다.*

## <a name="symlink_status"></a><a name="symlink_status"></a>symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

함수는 *pval*과 연결된 pathname 심볼 링크 상태, 파일 형식 및 사용 권한을 반환합니다. 함수는 선택한 파일이 `status(pval)` 아니라 심볼링크 자체가 테스트된다는 점을 제외하면 동일하게 작동합니다.

## <a name="system_complete"></a><a name="system_complete"></a>system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

이 함수는 필요에 따라 루트 이름과 연결된 현재 디렉터리를 고려하는 절대 경로 이름을 반환합니다. \(POSIX의 경우 함수가 `absolute(pval)`반환됩니다.\)

## <a name="temp_directory_path"></a><a name="temp_directory_path"></a>temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

이 함수는 임시 파일을 포함하는 데 적합한 디렉터리의 경로 이름을 반환합니다.

## <a name="u8path"></a><a name="u8path"></a>u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

첫 번째 함수는 동일하게 `path(source)` 작동하며 두 번째 함수는 `path(first, last)` 파일 시스템이 무엇이든 간에 각 경우에 선택한 소스가 UTF-8로 인코딩된 char elements의 시퀀스로 수행된다는 점을 제외하면 동일하게 작동합니다.

## <a name="weakly_canonical"></a><a name="weakly_canonical"></a>weakly_canonical

```cpp
path weakly_canonical(const path& p);
path weakly_canonical(const path& p, error_code& ec);
```
