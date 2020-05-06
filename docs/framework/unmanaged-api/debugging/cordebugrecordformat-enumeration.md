---
title: CorDebugRecordFormat 列挙体
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
ms.openlocfilehash: cfbd856c73ab10642a7cf7c16cfb2d70e7fe9756
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795730"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="ad4f8-102">CorDebugRecordFormat 列挙体</span><span class="sxs-lookup"><span data-stu-id="ad4f8-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="ad4f8-103">ネイティブ例外デバッグ イベントに関する情報を格納するバイト配列内のデータの形式を示します。</span><span class="sxs-lookup"><span data-stu-id="ad4f8-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad4f8-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad4f8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="ad4f8-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ad4f8-105">Members</span></span>  
  
|<span data-ttu-id="ad4f8-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ad4f8-106">Member</span></span>|<span data-ttu-id="ad4f8-107">説明</span><span class="sxs-lookup"><span data-stu-id="ad4f8-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="ad4f8-108">データは、32 ビット Windows 例外レコードです。</span><span class="sxs-lookup"><span data-stu-id="ad4f8-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="ad4f8-109">データは、64 ビット Windows 例外レコードです。</span><span class="sxs-lookup"><span data-stu-id="ad4f8-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad4f8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="ad4f8-110">Remarks</span></span>  
 <span data-ttu-id="ad4f8-111">列挙体のメンバーは、 `pRecord`引数のバイト配列の形式を示すために、 [DecodeEvent](icordebugprocess6-decodeevent-method.md)メソッドに渡されます。 `CorDebugRecordFormat`</span><span class="sxs-lookup"><span data-stu-id="ad4f8-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad4f8-112">この列挙型は .NET ネイティブのデバッグ シナリオのみで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="ad4f8-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad4f8-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="ad4f8-113">Requirements</span></span>  
 <span data-ttu-id="ad4f8-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad4f8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad4f8-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad4f8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad4f8-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad4f8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad4f8-117">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad4f8-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad4f8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad4f8-118">See also</span></span>

- [<span data-ttu-id="ad4f8-119">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="ad4f8-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
