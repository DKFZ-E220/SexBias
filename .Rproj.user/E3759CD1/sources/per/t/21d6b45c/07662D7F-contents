#' Load HNSCatlas Data
#'
#' This function loads the HNSCatlas dataset from the package's external data directory.
#'
#' @return A data frame containing the HNSCatlas dataset.
#' @examples
#' HNSCatlas <- load_HNSCatlas()
load_HNSCatlas <- function() {
  filepath <- system.file("extdata", "HNSCatlas.rds", package = "HNSCatlas")
  if (file.exists(filepath)) {
    readRDS(filepath)
  } else {
    stop("HNSCatlas data file not found. Please ensure the package is installed correctly.")
  }
}
