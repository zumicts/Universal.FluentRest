# Universal.FluentRest

Rest library for consuming apis in a fluent and strong typed manner.

## Example

*Request object:*

    /// <summary>
    /// Returns all the IMDb movie reviews for the specified movie.
    /// </summary>
    public class MovieReviewsRequest : RestObject<YtsResponse<YtsReviewsData>>
    {
        public MovieReviewsRequest(uint movieId)
        {
            this.Url("https://yts.to/api/v2/movie_reviews.json").Query("movie_id", movieId);
        }
    }
    
*Utilizing object:*

    var response = await new MovieReviewsRequest(25).ToResponseAsync(); 

## TODO

- [x] Xml deserializer
- [x] Allow posting JSON content.
- [ ] Allow posting XML content.
- [ ] OAuth
