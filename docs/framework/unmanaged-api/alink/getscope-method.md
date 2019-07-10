---
title: GetScope メソッド
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3c3142ca12789b086bcd8b5a9c00c943264ae7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741858"
---
# <a name="getscope-method"></a><span data-ttu-id="15c4b-102">GetScope メソッド</span><span class="sxs-lookup"><span data-stu-id="15c4b-102">GetScope Method</span></span>
<span data-ttu-id="15c4b-103">インポート スコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="15c4b-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15c4b-104">構文</span><span class="sxs-lookup"><span data-stu-id="15c4b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="15c4b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15c4b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="15c4b-106">インポート先のアセンブリの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="15c4b-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="15c4b-107">インポートするファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="15c4b-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="15c4b-108">インポートする 0 から始まるスコープです。</span><span class="sxs-lookup"><span data-stu-id="15c4b-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="15c4b-109">受信[IMetaDataImport インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)スコープのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="15c4b-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15c4b-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="15c4b-110">Return Value</span></span>  
 <span data-ttu-id="15c4b-111">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="15c4b-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15c4b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="15c4b-112">Requirements</span></span>  
 <span data-ttu-id="15c4b-113">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="15c4b-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c4b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="15c4b-114">See also</span></span>

- [<span data-ttu-id="15c4b-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15c4b-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="15c4b-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15c4b-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="15c4b-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="15c4b-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
