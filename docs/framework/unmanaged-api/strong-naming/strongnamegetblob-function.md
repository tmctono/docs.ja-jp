---
title: StrongNameGetBlob 関数
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e23232b55a841672ee193b980c310995ba688e00
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160993"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="b7668-102">StrongNameGetBlob 関数</span><span class="sxs-lookup"><span data-stu-id="b7668-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="b7668-103">指定したアドレスにある実行可能ファイルのバイナリ表現が、指定したバッファーに入れられます。</span><span class="sxs-lookup"><span data-stu-id="b7668-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="b7668-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="b7668-104">This function has been deprecated.</span></span> <span data-ttu-id="b7668-105">使用して、 [iclrstrongname::strongnamegetblob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="b7668-105">Use the [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7668-106">構文</span><span class="sxs-lookup"><span data-stu-id="b7668-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7668-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b7668-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="b7668-108">[in]読み込まれる実行可能ファイルへの有効なパス。</span><span class="sxs-lookup"><span data-stu-id="b7668-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="b7668-109">[in]実行可能ファイルを読み込むバッファー。</span><span class="sxs-lookup"><span data-stu-id="b7668-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="b7668-110">[入力、出力]最大サイズ (バイト単位) を要求された`pbBlob`します。</span><span class="sxs-lookup"><span data-stu-id="b7668-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="b7668-111">関数が戻るとき、実際のサイズをバイト単位の`pbBlob`します。</span><span class="sxs-lookup"><span data-stu-id="b7668-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7668-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="b7668-112">Return Value</span></span>  
 `true` <span data-ttu-id="b7668-113">正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="b7668-113">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7668-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7668-114">Remarks</span></span>  
 <span data-ttu-id="b7668-115">場合、`StrongNameGetBlob`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="b7668-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7668-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="b7668-116">Requirements</span></span>  
 <span data-ttu-id="b7668-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7668-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7668-118">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b7668-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b7668-119">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b7668-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b7668-120">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="b7668-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7668-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7668-121">See also</span></span>

- [<span data-ttu-id="b7668-122">StrongNameGetBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="b7668-122">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="b7668-123">StrongNameGetBlobFromImage メソッド</span><span class="sxs-lookup"><span data-stu-id="b7668-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="b7668-124">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7668-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
