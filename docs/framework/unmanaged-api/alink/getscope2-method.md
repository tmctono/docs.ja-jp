---
title: GetScope2 メソッド
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: a5b080443be94d5a298cc67591914d87470e6f48
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447185"
---
# <a name="getscope2-method"></a><span data-ttu-id="d6679-102">GetScope2 メソッド</span><span class="sxs-lookup"><span data-stu-id="d6679-102">GetScope2 Method</span></span>
<span data-ttu-id="d6679-103">インポートスコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="d6679-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6679-104">構文</span><span class="sxs-lookup"><span data-stu-id="d6679-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="d6679-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6679-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d6679-106">ターゲットアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="d6679-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d6679-107">インポート元のファイルの ID。</span><span class="sxs-lookup"><span data-stu-id="d6679-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="d6679-108">インポートする0から始まるスコープ。</span><span class="sxs-lookup"><span data-stu-id="d6679-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="d6679-109">指定されたスコープの[IMetaDataImport2 インターフェイス](../metadata/imetadataimport2-interface.md)インターフェイスへのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d6679-109">Receives pointer to [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6679-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="d6679-110">Return Value</span></span>  
 <span data-ttu-id="d6679-111">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="d6679-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6679-112">要件</span><span class="sxs-lookup"><span data-stu-id="d6679-112">Requirements</span></span>  
 <span data-ttu-id="d6679-113">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="d6679-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6679-114">参照</span><span class="sxs-lookup"><span data-stu-id="d6679-114">See also</span></span>

- [<span data-ttu-id="d6679-115">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6679-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d6679-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6679-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d6679-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="d6679-117">ALink API</span></span>](index.md)
