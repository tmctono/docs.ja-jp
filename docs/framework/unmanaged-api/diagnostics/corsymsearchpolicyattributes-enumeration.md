---
title: CorSymSearchPolicyAttributes 列挙体
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
ms.openlocfilehash: 786e53d43ecde0bc3a97fadb77184d25d41430bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178349"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="399ce-102">CorSymSearchPolicyAttributes 列挙体</span><span class="sxs-lookup"><span data-stu-id="399ce-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="399ce-103">シンボル リーダーの検索を実行するときに使用するポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="399ce-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="399ce-104">これらの定数は、[メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)によって使用されます。 [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)</span><span class="sxs-lookup"><span data-stu-id="399ce-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="399ce-105">信頼できないソースからプログラム データベース (PDB) ファイルを開くと、セキュリティ上のリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="399ce-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="399ce-106">構文</span><span class="sxs-lookup"><span data-stu-id="399ce-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="399ce-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="399ce-107">Members</span></span>  
  
|<span data-ttu-id="399ce-108">メンバー</span><span class="sxs-lookup"><span data-stu-id="399ce-108">Member</span></span>|<span data-ttu-id="399ce-109">説明</span><span class="sxs-lookup"><span data-stu-id="399ce-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="399ce-110">レジストリにシンボル検索パスを照会します。</span><span class="sxs-lookup"><span data-stu-id="399ce-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="399ce-111">シンボル サーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="399ce-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="399ce-112">Debug ディレクトリで指定されたパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="399ce-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="399ce-113">.exe ファイルがある場所で PDB を検索します。</span><span class="sxs-lookup"><span data-stu-id="399ce-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="399ce-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="399ce-114">Requirements</span></span>  
 <span data-ttu-id="399ce-115">**ヘッダー:** コーシム.idl,コーシム.h</span><span class="sxs-lookup"><span data-stu-id="399ce-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399ce-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="399ce-116">See also</span></span>

- [<span data-ttu-id="399ce-117">シンボル ストア診断列挙体</span><span class="sxs-lookup"><span data-stu-id="399ce-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
