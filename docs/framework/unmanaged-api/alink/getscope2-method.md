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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c0abc63610f3f1ed6e8a556c44ee15edc1ea20b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741839"
---
# <a name="getscope2-method"></a><span data-ttu-id="569ac-102">GetScope2 メソッド</span><span class="sxs-lookup"><span data-stu-id="569ac-102">GetScope2 Method</span></span>
<span data-ttu-id="569ac-103">インポート スコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="569ac-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="569ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="569ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="569ac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="569ac-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="569ac-106">ターゲット アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="569ac-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="569ac-107">インポート元のファイルの ID。</span><span class="sxs-lookup"><span data-stu-id="569ac-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="569ac-108">インポートする 0 から始まるスコープです。</span><span class="sxs-lookup"><span data-stu-id="569ac-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="569ac-109">ポインターを受け取る[IMetaDataImport2 インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)指定のスコープのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="569ac-109">Receives pointer to [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="569ac-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="569ac-110">Return Value</span></span>  
 <span data-ttu-id="569ac-111">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="569ac-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="569ac-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="569ac-112">Requirements</span></span>  
 <span data-ttu-id="569ac-113">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="569ac-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="569ac-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="569ac-114">See also</span></span>

- [<span data-ttu-id="569ac-115">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="569ac-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="569ac-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="569ac-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="569ac-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="569ac-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
